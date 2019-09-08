---
layout: post
title: "Wiki Strategies: Data Mining 2"
date: 2012-08-01
categories: [ software]
---
(This post has been edited to remove company-specific information)

To understand why the following is a tweak, you need to understand how the Fosswiki works. Pages on the wiki are stored as simple text files. The text file contains static content, wiki-instructions and wiki-specific formatting. When you request a page, the Wiki's engine executes the instructions, interprets the formatting and renders the result as HTML - which is then shown to the user: you.

In FossWiki, if you pass the parameter "raw=on" in the URL only the raw content of  a page is returned. This is much faster since no instructions have been processed and no formatting interpreted.

The AJAX searches we used to improve page loads (backstory) first loaded the page they were interested in and then parsed the page's content to get the required information. For dynamic searches this is necessary - the page's content would be a search which when rendered would contain results. However, for static content - loading the page was unnecessary and at times a nuisance since we'd have to parse complicated HTML formatting.

While developing a  system to display results of a Vote System for our wiki, we needed to parse meta data in pages - not necessarily the rendered content.  We changed the AJAX search to first fetch the raw view of the page. This made our search faster and the subsequent content parsing easier.
