---
layout: post
title: "Logseq for Task Management"
date: 2023-09-16
categories: [ software ]
tags: [ tutorial ]
---

Hello!,

I've been using [Logseq](https://logseq.com/) for Task Management for the past several months and thought I'd write a post about the features I use and love about it.

## What this post is
* It is an incomplete list of features I think a good Task Management system should support with examples of how Logseq does them. Where possible, I include a few tips.

## What this post is not
* It is not about the benefits of personal Knowledge or Task Management .
* It is not a comprehensive list of what features a Task Management System should have.
* It is not an introduction to Logseq

## Intended audience
* This post is for people who are already sold on the merits of Knowledge & Task Management. And have tried tools like Notion, Todoist, Obsidian, Roam Research etc. 

I too have tried these tools and switched to Logseq because of the following reasons:
- It is open source
- Its license is not restrictive and allows me to use it for Personal projects and at work
- Its content is stored as markdown so my notes are not in some proprietary format that I cannot later decipher
- The community around the tool is kind (and active)

## How to read this post
In most cases, I've used a little text to introduce a GIF. The GIFs serve as a visual guide or example of the feature I'm demonstrating. 

## References/Credits
Almost everything I've learnt about Logseq has been from [OneStuttering](https://twitter.com/OneStuttering). His [videos](https://www.youtube.com/@OneStutteringMind/featured) are a treasure trove of information

## Features

### Easy Learning Curve
A Task Management System should be easy to use. You should discover new features as you mature. 

Logseq does this well. It starts with a journal view. Adding Tasks is as trivial as creating a simple list. As you learn more about the tool and task management, you'll find yourself thinking: "I wish I could do this" and discover that Logseq supports it.

Pro Tip: Start small. Don't try to build a system overnight. Doing so will make both adopting the tool harder and take you down a rabbithole of customisations you don't need.

### Create and Manage Tasks
At its most basic level, a Task Management System should allow you to create and manage tasks (i.e. set statuses). 

In Logseq, the blocks you add can become tasks with just a couple of key strokes `CTRL+ENTER`

Pro Tips:
- Change the settings to switch to the workflow you prefer
- Install the "Task Management Shortcuts" plugin - it allows you a few more statuses such as CANCELLED and WAITING
- There are other very opinionated plugins if you want to try them. Explore the marketplace!

* [Create Tasks GIF](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3nh01u679gjz3yfn81nn.gif)


![Create Tasks](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3nh01u679gjz3yfn81nn.gif)

### Prioritise Tasks
You should be able to prioritise tasks so that you can do the important stuff first. 

Logseq ships with some default priorities: `/A`, `/B` or `/C` . Adding your own custom priorities is trivial - at the end of the day, these are just links to a page.

![Prioritise tasks](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/niciqsfloy98vpiae9d8.gif)

### Schedule tasks
You should be able to schedule tasks to another day.

LogSeq allows you to do this using `/schedule` - you can pick the date and time when you want the task to surface and it will show up on that day in the journal

![Scheduling Tasks](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/dogj49uykkexc2ovz6we.gif)

### Create Repeatable Tasks
You will want to schedule some tasks to repeat every day or week. 

While Logseq's scheduling capabilities are simple, they are more than sufficient for my needs.

![Schedule Repeatable tasks](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/v5bj6rekvot8ybrqv093.gif)

ProTip: Use annual repeating tasks within a person's page to add birthday and anniversary reminders.

### Tagging and Projects
To avoid navigating huge lists, being able to categorise tasks is important. Most task management systems support this feature but put it behind a paywall or worse, a subscription.

Since Logseq automatically creates links to pages, these can then be used to categorise tasks. So you can now categorise tasks by tagging them with project names and then put references, links etc. in the project's pages

![Categorize tasks](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/uf4ckktqeilgxe7m31bw.gif)

Pro Tip 1: ALWAYS categorise tasks even if the project doesn't exist. You can always add details about the project later. Avoid generic categorisations like `misc, general` as much as possible. 

Pro Tip 2: Add a "trigger" link to each task which will take you to the trigger for this task - could be a JIRA ticket, email or IM message. Will be useful when you are trying to trace a task back to why you did it.

### Assigning Tasks
You should be able to assign tasks to others and track their progress.  

Almost every system today forces you to add users to accomplish this. In my case, that is never what I actually need. When I say others, I don't mean that I want other users to see the tasks I've assigned them. Only that my dashboard should allow me to add tasks and indicate that others are working on them.

In Logseq, a person is just a block or a page like any other. So tagging a task as being done by another is trivial. 

Pro tip: Write the task in plain english as `#X to do Y` rather than `do Y #x` - the first is much more readable and will make sense months down the line

![Assign users](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/t7unaypopbfr8dfn4xfs.gif)

### Create Custom Dashboards
Most Task Management Systems are strongly opinionated. 

Some Knowledge Management systems on the other hand, allow you too much customisation: so much so that you end up wasting hours on tools like Notion tweaking how it looks. Logseq's powerful query system allows you to build dashboards that will surface the content you are interested in. 

_The embedded gif is sometimes not working. Here is a direct [link](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3qd1lz5d84i1010gocvw.gif) to the image_

![Create Dashboard](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/3qd1lz5d84i1010gocvw.gif)

_In the GIF above, I first add a `/query` to list all TODOs linked to my project. Then, realising a linked block is not a TODO, I go update it and verify that it shows up as well_

Pro Tip 1: People are just Pages so adding the same query to a person will give you a person-specific dashboard of tasks you've delegated to someone

![Person Dashboard](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/d1ckh9u86vyf8j0dca22.gif)

Pro Tip 2: I prefer a table like display for dashboards but the width available is not enough. To get rid of the spaces on either side, press `t+w` - this narrows the margin on either side. If this doesn't help, install a theme or play around with the custom.css file in the root folder of your Logseq graph to get the look-and-feel you want.

![Dashboard table](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/n5nrwgi6u6w5gzxvjilw.gif)

### Copy and Move Tasks
You should be able to
* Copy a task to another day
* Move it to another day
* Postpone to another day
* Carry-over to another day

This, in my mind, is one of its most powerful features in Logseq that allows me to use it as a Task Management tool

* Copy: Select the text of the task and copy it  over to the target
* Move: Select the text. Cut and paste it in the target
* Postpone: First, create a section called "Postponed" in the  journal of the day you are postponing from, now copy the reference to the task (Click on the task but don't select any text and then press `CTRL+C`) and paste the reference in the new day
* Carry-over: The same as above but in the original day you don't move the task to the "Postponed" section

_The embedded gif is sometimes not working. Here is a direct [link](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/um5y7ppykg04fz3nb8c1.gif) to the image_


![Copy Move Postpone & carry over Task](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/um5y7ppykg04fz3nb8c1.gif)

_NOTE_ : Anything you add under a copied reference won't show up as a linked reference in the original topic. So you may want to add explicit links

Pro Tip: 90% of the time, my tasks remain in the journal and are available in projects through Logseq's linking or my dashboards. Sometimes however, I "move" the task from the journal to the project. Doing so is again trivial. Copy the text over and add a link to the journal instead.

I typically do this when I want to breakdown/plan a large project and want a single canvas to plan in. 

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hi963876xe2usr8f2a7b.gif)

### Breakdown Tasks
You should be able to breakdown a task. Indefinitely.

This is again where most Task Management Systems I've used in the past don't match up to Logseq. Logseq's blocks-based approach allows you to add children indefinitely.

![Break down Tasks](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/et16emdtsdqhh06oofug.gif)

### Narrow or Broaden focus
Seeing a huge list of tasks is sometimes distracting. You should be able to narrow or broaden your focus as you wish. 

![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/d4iompemez5okfp5sswd.gif)

### Mobile Support
Task Management systems should allow you to add tasks when you think of them. This means Mobile support and the ability to sync.

ProTip: Logseq has a paid feature which allows you to sync between devices. If you'd rather not pay, you could use one of two hacks.

* Add your graph to a git repository and sync using Github as source
* Move your graph to Google Drive and sync using Drive's own syncing feature. For Android, I found the app "DriveSync" very easy to use and you only need to pay a one-time fee instead of a subscription for the pro version.

## Features it doesn't have

### Chaining Tasks
"Getting Things Done" is the book my Task Management is most inspired from. The first tool that checked almost every box was [mGSD](https://mgsd.tiddlyspot.com/#mGSD) - one feature it had that Logseq does not is the ability to create a chained sequence of tasks. Tasks with dependencies which need to be accomplished first are greyed out and when the dependency is marked completed, the next task becomes active. This [feature is being discussed](https://discuss.logseq.com/t/dependencies-task/738) but is not available yet

## Risks
* Logseq is opinionated about blocks. So there are Bullets everywhere!! - Thinking in this way can, at first, be challenging and some may never be able to do it.  
* Logseq stores everything in one flat folder structure. While you can create hierarchies in Logseq, the underlying files will all be at one level. This can also take some getting used to and has been [highlighted](https://discuss.logseq.com/t/feature-request-creation-of-folders-and-subfolders-will-make-knowledge-management-more-feasible/3446/8) [by many](https://discuss.logseq.com/t/proposal-changing-how-namespaces-function-in-logseq/3727) as a concern. This decision also makes it difficult to work on the files directly outside of Logseq - like say copying all the content about a Project someplace else. If this worries you, avoid Logseq for now. 