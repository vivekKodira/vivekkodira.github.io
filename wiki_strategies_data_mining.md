(2012: This post has been edited to remove company-specific information. 

We started with basic searches and eventually built a comprehensive dashboard with asynchronous searches to get every kind of data imaginable about our wiki. Was fun to create and to see in action. Even got a crowd clapping during a demo to aspiring teams who were starting out on their own wikis)

NOTE: What follows is my experience in trying to get usage statistics out of our wiki. There are probably better and easier ways to do this - so please do experiment.

Why would you collect data from within a wiki? Well, for several reasons...
When we started our wiki, we didn't have an idea what it would end up becoming. We envisaged it as a forum where people would share opinions, views, tutorials and tips. But as I'd mentioned in the last post, the most popular and knowledge-generating feature of the wiki ended up being the FAQ section. This difference in growth can be observed if you watch the wiki on a day-to-day basis but is difficult to quantify without statistics. Knowing what our most popular feature was and the rate at which it was growing helped us decide where to concentrate our efforts and to plan better
Another example is when we had to choose which of our team members to nominate for awards. Every quarter, we try and nominate the people who contribute the most for an internal award.
The third is an idea I read in a Web 2.0 blog and thought was interesting. The theory is that over time and with enough data from wikis and blogs, we can find which individuals have contributed the most knowledge content to a particular tool, technology, framework or domain. This helps us find SMEs (Subject Matter Experts) using dependable data rather than just his/her resume and years of experience. These folks are, for obvious reasons, also more likely to be helpful.
So, for these reasons and others, it is useful to collect data on wiki usage. There are several ways to go about it...
The first and easiest is to simply use the in-built statistics functionality of your wiki engine. Copy the data to an XLS and you have a monthly chart of Views Vs. Updates and the people who contributed the most that month. The flaws with the approach above are two: 
It does not give information by category - i.e. you cannot answer questions like: "Were pages under Framework A the most updated or were there more updates in topics under Framework B?". 
Also, it does not give information about who 'added' information. Only about who has the most edits. 
For example, consider a user: 
Expert1 who added a topic about 'Single Sign On' - Expert1 prepares the content, creates a topic and goes away. (Total number of edits:1. )
Editor2 comes along and decides to correct phrases and presentation. He saves continually and repeatedly until happy with the topic. (Total number of edits: n. )
The statistics page mentioned above is going to show Editor2 as a larger contributor than Expert1.
The alternative is to build custom searches to gather statistical data. 
Using the SEARCH feature to crawl through all the pages of the web and pull out information about topic 'creators', one can derive statistics about who has created the most content - not just edited it.
Fosswiki specific example: replace searchString by the user name

```
%CALC{$SET(dynamicCount,0)}%

%SEARCH{ ".*" scope="topic" regex="on" topic=".*" nonoise="on" limit="all" format="$percntCALC{$IF($FIND($GET(searchString),$createusername,0)>0, [[$topic]]$SET(dynamicCount,$EVAL($GET(dynamicCount)+1)),<nop>)}$percnt"}%

Total Topics created: %CALC{"$GET(dynamicCount)"}%
```

Or one could get the number of children for a topic (This will only work if your web's topics are properly categorized)
Fosswiki specific example:
```
%CALC{$SET(frameworksTotal,0)}%
%METASEARCH{type="parent" web="%WEB%" topic="PutTopicNameHere" title="" format="$percntCALC{$SET(frameworksTotal,$EVAL($GET(frameworksTotal)+1))}$percnt" }%
Number of Frameworks: %CALC{$GET(frameworksTotal)}%
```

A third variation of such searches is to use it to derive time-based results. i.e. you enter a date range and the results display how many topics of a certain kind were added in that range. 
The best and most accurate way of deriving usage statistics is to take a dump of your wiki and parse the back-end files to get complete information on all the versions of a file. This is also probably the only way, you can get information about who edited version x of a topic). Will add more on this approach when I figure it out myself... :).