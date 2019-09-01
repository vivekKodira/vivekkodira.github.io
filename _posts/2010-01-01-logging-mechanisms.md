---
layout: post
title: "Logging Mechanisms"
date: 2010-01-01
---
(2012: This one is edited to remove any content specific to the company I was in at the time)


Some of the content below may be inaccurate. My apologies if they are. 

I recently attended a session on IBM's WebSphere Application Server. The second day of the session dealt only with problem analysis. There were a few things about the logging mechanism that one noticed and would be useful in any tool/application.

## Configurable
The user is allowed to configure different levels of logging. He can choose to log only errors, log errors and warnings, log errors, warnings and information. (There were 3 or 4 more such levels). The product also has features such as allowing the user to configure the size of a log file (after exceeding which, another physical file should be used) and specifying how many files to retain. 

## Built over a framework
Advantage: This allows developers of the application to concentrate on what is important - developing the application. Unless the logging being implemented is dictated by business requirements, the process of logging should be completely transparent to developers. 

## Separation of application generated logs and user logs
The advantages are obvious. Typically one could create three different kinds of logs: error (application/fatal), message (business/validation) and debug(flow). When doing this however, make sure you keep the API distinct and simple. Developers, not knowing which method to use in which situation, may end up using them interchangeably. This will result in every log containing every kind of data. Support folks will not know which to search when trying to analyze problems.

## Tools and Processes to ensure logs are useful
This was, for me, the most impressive part. At least 4 different tools were showcased in the session. Each one helped interpret and analyse a different kind of error. One even suggested steps to avoid such errors in the future. 

Here are some features/processes that I feel an application's logging mechanism should contain:

## Rollover
Configure logs so that no one log file becomes too heavy. Arrive at the size considering your log-interpreter's and application server's limitations. Once the file has reached its specified limit, roll-over to the next. 

## Extract
Put a system job that regularly scans the m/c for such 'done-with' log files and moves (not copy) them to another location. 

## Interpret
Configure a custom-made log interpreter(s) to automatically read and log these errors to a database - categorized by type (m/c, application, user), severity, time, user (if ok according to policy) ......(and other parameters if required).

## Report
Configure a reporting tool to periodically report errors to the concerned people. (M/C errors would go to System Admins, Application errors to the support team and user errors to a kind of Customer Support Rep).

## Feedback
Each then sends back suggestions on fixes, improvements or tweaks to avoid the error in the future. These are stored in another database that is a sort of a master database of errors and possible fixes.

## Consolidate and implement
Review this data and send feedback to the same people as earlier so they can implement processes that avoid the error occurring again.

Suggestions/Feedback welcome :),

