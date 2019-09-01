---
layout: post
title: "Configuration Management - Managerial Considerations"
date: 2012-08-01
categories: [ software ]
tags: [configuration-management]
---

3 of the 12 steps in Joel Spolsky's article ["The Joel Test: 12 Steps to Better Code"](http://www.joelonsoftware.com/articles/fog0000000043.html) (written in 2000) dealt with builds. Today, everyone agrees on the need for configuration management (CM) and continuous integration (CI). However, my experience has also been that configuration management is setup and then completely ignored until things go wrong. 

This neglect is unfortunate considering how critical configuration management can be. In this post, I attempt to list down the points teams would want to consider when choosing a CM strategy. 

* Note: 
The points listed below are neither new nor radical. Instead, the aim is to document a checklist which could be used as a refresher.

Rather than delve into technical questions (such as whether to choose a central or distributed version control system), this post only considers 'managerial' choices one would have to make.

- [Cycling responsibility vs. a dedicated CM team:](#cycling-responsibility-vs-a-dedicated-cm-team)
- [Team size:](#team-size)
- [Build Vs. Buy:](#build-vs-buy)

### Cycling responsibility vs. a dedicated CM team: 

Small teams simply cycle the responsibility of being the configuration manager to everyone in the team. This strategy works well for experienced developers. However, when you consider that the same choices will be made over and over again, it quickly becomes obvious that this approach would backfire for inexperienced developers or large teams. The risks and costs involved multiply. 

**Recommendation**: Cycle responsibilities for small teams with experienced developers. If you have inexperienced members, have several teams and/or belong to a mid-sized organization, invest in a dedicated team for configuration management. The team can then learn and evolve over time - helping improving the throughput of the development team.

### Team size: 
Since support teams do not contribute (directly) towards the bottom line, there is a tendency to keep them small. This is a decision which often has disadvantages in the long run. A very small CM team will constantly be 'catching-up'. It will not find time to improve its functioning or its members' skills. On the other hand, a team with some slack would be able to cycle folks into and out of stressful assignments. Such teams would also have time to look into not-urgent (but critical) aspects such as automation.

**Recommendation**: Start small, invest in automation upfront. Increase team-strength to meet demand. When the team's size reaches equilibrium, add some slack (which can then be used for better scheduling and driving innovation). Re-evaluate periodically.

**Contract**:
One danger that members of CM teams are susceptible to is complacency. Many of the requests coming to the team, while taking time and effort to resolve, will be repetitive in nature. Team members become bored and demotivated. They do not put efforts to improve processes which work acceptably but not yet optimally.

**Recommendation**: Establish clear service level agreements (SLA) for the team. Mandate publishing of periodic reports detailing the number and nature of requests being serviced. Use these to evaluate the team's effectiveness, decide on mandatory/stretch goals and to identify opportunities for automation.

### Build Vs. Buy:
Creating a dedicated CM team will involve several challenges. These can be straightforward ones such as finding developers willing to invest in configuration management as a career or long-term ones such as charting career paths for such developers. Ensuring such teams  continuously improve, follow industry best practices and keep up to date with technology are also important.

**Recommendation**: For teams willing to try it, there are several 3rd party solutions which give you the option of buying configuration management as a service. All the associated technical and management challenges are taken care of, allowing your team to concentrate on what it does best: create. 

Here is a list of such companies:
* [Electric Cloud](http://www.electric-cloud.com/)
* [Atlassian Bamboo](http://www.atlassian.com/software/bamboo/overview)
* [CloudBees](http://www.cloudbees.com/)
* [TravisCI](https://travis-ci.org/)
* [CodeShip.IO](https://www.codeship.io/)
* [ShiningPanda.CI](https://www.shiningpanda-ci.com/)
* [Wercker](http://beta.wercker.com/)
