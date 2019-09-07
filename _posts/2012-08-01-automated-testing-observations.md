---
layout: post
title: "Automated Testing: Observations"
date: 2012-08-01
categories: [ software ]
tags: [testing]
---

*In this post, I document some observations on automated UI-based testing. Note: The intended audience for this post are folks who are familiar with (but are not experts on) automated testing.* 

A word of caution, UI-based automation testing should only form a minor part of your team's test arsenal. Such tests are brittle, expensive, time consuming, have lower returns and are redundant (several different tests will end up testing the same piece of code over and over). More effort should be spent on non-ui-service-level and unit testing. Test Driven Development (TDD) is best.

- [Develop the UI keeping automated testing in mind.](#develop-the-ui-keeping-automated-testing-in-mind)
- [Rather than a one-size fits all approach, create several tailor-made test suites to cater to specific needs.](#rather-than-a-one-size-fits-all-approach-create-several-tailor-made-test-suites-to-cater-to-specific-needs)
- [Ensure that the system-under-test is reset to a predefined state before and after tests.](#ensure-that-the-system-under-test-is-reset-to-a-predefined-state-before-and-after-tests)
- [References/Further reading:](#referencesfurther-reading)

### Develop the UI keeping automated testing in mind. 

Add appropriate identifiers (classes and IDs) to HTML elements which are used for any kind of input/navigation or have some other significance (and so may be selected and validated during test execution).

Not doing so will mean that testers will need to use convoluted methods to identify elements (ex: xpath) during automation. Minor changes to element positions will break tests. Identifiers are also useful when screens use asynchronous code to load content. Tests can check (and if necessary wait) for elements to be loaded before proceeding with further execution.

### Rather than a one-size fits all approach, create several tailor-made test suites to cater to specific needs. 

What a test suite is intended for should influence the nature of the tests within it. For instance, sanity testsuites should cover breadth of a solution and not so much its depth. 
  
Concerned about the stability of the product, teams in my earlier organization were asked by management to create and maintain sanity tests. These tests would be executed whenever teams integrated new modules to the baseline. Some teams added very detailed tests which made maintaining the test suite difficult. Over time, this resulted in project delays and eventually it became common practice to take deviations from the process.

### Ensure that the system-under-test is reset to a predefined state before and after tests. 

If not done, changes in the underlying system's state will cause tests to fail unpredictably reducing user confidence in the tests themselves.

While it is tempting to use the tests themselves to create the system from scratch, this would bring in complications such as enforcing a particular order to test execution. Ensure tests can be run as independently as possible even if they need to do their own setup. 
Rather than only depending on the tool's 'record and replay' aspects, use logic-based methods available in the automation tool to store and validate runtime values later 
In my earlier team, novice developers often made the mistake of writing tests which performed a transaction and then validated it later by selecting the first record in resulting list (assuming the latest transaction would appear first). Selenium provides the !storeText command which could be used to store such a transaction's reference.

### References/Further reading: 

- http://martinfowler.com/articles/nonDeterminism.html
- http://www.mountaingoatsoftware.com/blog/the-forgotten-layer-of-the-test-automation-pyramid
