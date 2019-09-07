---
layout: post
title: Automate a multi-window experience on iTerm2
description: Use AppleScript to automate creation of multiple sessions
categories: [software, tutorial]
tags: [iterm2, applescript, macOS, beginner]
---

## TLDR
This post is a tutorial. The final outcome will be a script that creates several sessions on a remote machine, running commands in parallel. Jump to the end to see the final script or read on for a step-by-step tutorial

## Why would you want iTerm automation?
Here is an example from my own workflow:

The installation script I'm testing these days launches several containers, creates folders with different user permissions and copies files back and forth between mounted folders.

These are the steps I need to do each time I begin testing

* Create 4 sessions in an iTerm tab
* ssh into the remote machine I'm testing*
* switch to sudo*
* Install the software I will need (`docker`, `docker-compose`, etc.)
* Configure `watch` to monitor docker containers in one session
* Configure `tree` to watch the folder structure in another
* Configure `watch` with `cat` to monitor some files in the third
* And run the installation script in the last container

*Repeated in each session!

You can see how doing this over and over becomes tedious. Shell scripts would be able to automate some steps above but not enough.

[AppleScript](https://developer.apple.com/library/archive/documentation/AppleScript/Conceptual/AppleScriptLangGuide/introduction/ASLR_intro.html) to the rescue!

## Hello world!
Let's start with a hello world.

* Create a file `hello_world.scpt` with the contents below:

```osascript
#!/usr/bin/osascript
tell application "iTerm2"
    set contentToPrint to "hello world"
end tell
do shell script "echo " & contentToPrint
```
* Run this script (`osascript hello_world.scpt`). You should see
`hello world` in the terminal

The code above is reasonably self-explanatory, so let's jump right into the next example. 

## Hello world .. again?

* Create a file `hello_world2.scpt` with the contents below:

```osascript
#!/usr/bin/osascript
tell application "iTerm2"
    tell current session of current tab of current window
        write text "echo 'hello world again!'"
    end tell
end tell
```

* Run this script (`osascript hello_world2.scpt`). You should see 

```
~ osascript hello_world2.scpt
echo 'hello world again!'
~ echo 'hello world again!'
hello world again!
```

Though the final output is similar, this version printed a few more lines as well. How is this different from the earlier script? 

Press the 'up arrow' to see the last command in the terminal's history. It'll display 

`echo 'hello world again'`. 

Press up again and **this** time you'll see 

`osascript hello_world2.scpt`. 

The difference then is this: `hello_world2.scpt` executed the instruction we gave it on the terminal. The `echo` got added to the terminal history.

Personally, I prefer this second approach  - it is both more readable and I want to be able to search for and execute these individual commands if I need to.

## Creating multiple sessions

Let's now automate creation of multiple sessions

* Create a file `sessions.scpt` with the content below

```osascript
#!/usr/bin/osascript
tell application "iTerm2"
    tell current session of current tab of current window
        split horizontally with default profile
    end tell
end tell
```

Run it and you'll see that it will divide the terminal into two horizontal sessions

Similarly, running a script with the content below will divide the terminal into two vertical sessions.

```osascript
#!/usr/bin/osascript
tell application "iTerm2"
    tell current session of current tab of current window
        split vertically with default profile
    end tell
end tell
```

## Sessionception!

You can issue commands to each session. Let's create two vertical sessions within each horizontal session. 

* Create a file `sessionsception.scpt` with the content below

```osascript
#!/usr/bin/osascript
tell application "iTerm2"
    tell current session of current tab of current window
        split horizontally with default profile
        split vertically with default profile
    end tell
    tell third session of current tab of current window
        split vertically with default profile
    end tell
end tell
```

The part that might be confusing is figuring out which is the second, third and fourth sessions. Just remember that sessions are not numbered in the order they are created. Session numbering is left-to-right on the first row and then similarly on subsequent rows. 

This is why even though the horizontal session was created second, when addressing it in the script, the command is `tell third session`


![session numbering](/assets/images/how-to-automate-a-multi/sessions.png)


## Back to the future

Let's jump ahead to the final script I need. Here it is below

```osascript
#!/usr/bin/osascript
tell application "iTerm2"
    tell current session of current tab of current window
        write text "setupTargetMc"
        write text "sshmc2"
        write text "sudo su"
        write text "./installStuff.sh"
        write text "watch -n1 'docker ps --format=\"{{.Names}} {{.Ports}} {{.Status}}\"'"
        split horizontally with default profile
        split vertically with default profile
    end tell
    tell second session of current tab of current window
        write text "sshmc2"
        write text "sudo su"
        write text "watch -n1 'tree -u -d  ~/.temp -L 3'"
        split vertically with default profile
    end tell
    tell third session of current tab of current window
        write text "sshmc2"
        write text "sudo su"
        write text "watch -n1 'cat ~/.temp/key'"
    end tell
    tell fourth session of current tab of current window
        write text "sshmc2"
        write text "sudo su"
        write text "clear"
    end tell
end tell
```

Much of the content above should be simple to understand by now. But here, if you need it, is a breakdown of some lines which may be unfamiliar 

* `write text "setupTargetMc"` - invokes `setupTargetMc` - an alias I've created beforehand to copy scripts I need (`installStuff.sh`) to the target machine
* `write text "sshmc2"` - invokes `sshmc2` - an alias I've created beforehand to `ssh` into the target machine
* `write text "./installStuff.sh"` - triggers `./installStuff.sh`. This is the script we copied over in the first step. It will setup the machine to my requirements including installations of all the software I need
* `watch` is used in several sessions, together with other commands, to continuously monitor docker containers, folder structures and contents of files


## Conclusion

iTerm automation has saved me a lot of time and effort. Hopefully, this post will motivate you to try it and give you the means to write your own. Best of luck!


## References

* [iTerm](https://www.iterm2.com/documentation.html)
* [AppleScript](https://developer.apple.com/library/archive/documentation/AppleScript/Conceptual/AppleScriptLangGuide/introduction/ASLR_intro.html)
* [watch](https://linuxize.com/post/linux-watch-command/)
* [tree](https://formulae.brew.sh/formula/tree)