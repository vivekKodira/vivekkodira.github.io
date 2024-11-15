---
layout: post
title: "The Home School"
date: 2024-11-15
categories: [ volunteering, tech ]
tags: [ tutorial ]
---

I recently worked with the folks at [The Home School](https://www.thehomeschool.in/) on their IT infrastructure, website & social media. This was a fun and rewarding experience. Something that helped me while I'm on my break. What follows is a summary of my observations & notes.

This is a school established in 1930 and nurtured since by some very passionate people. The principal first reached out to me for help on improving their social media but during our discussions, we discovered many more opportunities and worked on them as well. 

* Several schools have very outdated sites which some consultancy built for & now maintains for them. These are probably subscription based and put the school at the mercy of the consultancy for even minor updates.

* Most schools are still using regular gmail email addresses. These include famous ones like Baldwins (baldwingirls@gmail.com) & Frank Anthony public school Bangalore (faps1967@gmail.com). Some deductions from this are

	- These folks here are probably creating multiple email addresses for their internal processes (ex: sharing question papers). This is a bad practice and makes the institution vulnerable to hackers & bad actors
	- The institution is buying storage from Google to get over the 15GB limit associated with these emails. This is a repeating & unnecessary cost to the organisation. Or they are storing their files locally on computers - which is unsafe

## Goals

For [The Home School](https://www.thehomeschool.in/), my goals were to come up solutions which would be
  - less expensive from a cost perspective (avoid subscriptions)
  - classy & professional 
  - easy to maintain by the school itself

## Google Workspace
The first thing we did was registering for a [Google workspace](https://edu.google.com/intl/ALL_in/). Google workspaces are free for educational institutions. Pro Tip: having an existing domain and an established online presence may have helped our case. Our application was accepted!

With workspaces, Google offers tools meant specifically for educators such as Google classroom & Assignments ([Reference](https://edu.google.com/intl/ALL_in/for-educators/product-guides/?modal_active=none)). The educators at thehomeschool are exploring these further

## Website
We moved from the proprietary static site created by a consultancy to Google Sites. I considered a custom website or using [Wix](https://www.wix.com/) but Google sites won for two simple reasons
  - A site built with Google sites is childs play to maintain. Once the initial setup was done, one of the school's teachers took over and has been maintaining it since. Everything is drag-and-drop and even responsive out-of-the box.
  - Connecting a custom domain to the site is free in Google Sites but requires a paid subscription in Wix.

The only drawback so far with Google Sites is that you can't be very creative with design. But a good designer (someone not me) should be able to fix this. 

### Website Content

- An exercise I particularly enjoyed was interviewing all the teachers & creating [profiles](https://www.thehomeschool.in/about-school/our-teachers) for them. It was both humbling & inspiring.
- We reached out to old students for photographs and found a [treasure trove](https://www.thehomeschool.in/about-school).
- A professional photographer was hired and took some very beautiful photographs which I feel make the school's website much more appealing than the stock photos the consultancy had used

### Contact Forms 
We got past the limitation of Google sites being static by embedding [Google forms](https://www.google.com/forms/about/) on the website for [admissions](https://www.thehomeschool.in/admissions) & [alumni](https://www.thehomeschool.in/about-school/our-alumni) registrations. On form submission, scripts ensure that emails are sent to the internal email addresses. I did find the automation around Google forms not quite as powerful as I'd like and I'm considering alternative like Notion


## Users (Custom Email Addresses)
We created several users in the workspace (ex: enquiry@thehomeschool.in) and simply added mail forwarding to the old email addresses. The workspace admin can lock, pause & reset users or specify password policies making these safer than regular gmail addresses.

## Storage
We also now get 100 TB (yup 100!!!) of space for free. The admin can choose how to allocate this per user or just make all of it available to everyone in the organisation



## Social Media
* We consolidated the social media sites across [Facebook](https://www.facebook.com/thehomeschool.in), [Instagram](https://www.instagram.com/thehomeschool.in/), [Youtube](https://www.youtube.com/@thehomeschool1930) and [LinkedIn](https://www.linkedin.com/school/the-home-school-india). These were being managed by different folks and several were out of date. I recommend the use of tools such as a password manager or Google's Authenticator to better manage passwords.

* The teachers & I created a schedule for social media. (My original recommendation was to identify student volunteers but the school opted for a teacher)

* Facebook's Meta Business Suite (https://www.facebook.com/business/tools/meta-business-suite) is intuitive & easy to use. It allows you to schedule posts which will appear on both Facebook & Instagram.
* We divided the school's media appropriately. Earlier all the social media content was stored on laptops or uploaded to google drive. After some trial and error, we divided it up as follows:
  - Private media - Google photos & Drive (secure)
  - Public photo albums - Facebook (no space constraints!)
  - Public videos - Youtube (easy to embed)
  - Links to different social media content are now added to the site when necessary instead of being uploaded to the site directly. I also attempted to make an auto-updating iframe but only succeeded partially. There are paid solutions but I was reluctant to use them.
