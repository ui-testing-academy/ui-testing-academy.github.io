---
title: 'Approaches of UI testing'
description: 'Different ways of UI testing can be done: manual testing, record-and-replay testing, and model-based testing. We will explore the pros and cons of each approach.'
categories: [ ui-testing]
author: alex_zhukovich
---

UI Testing can be done in the following ways:
* Manual testing
* Record and replay testing
* Model-based testing

**Manual testing** is a type of software testing in which a tester performs actions for interaction with applications to check whether the software product is functioning correctly and meets all requirements. All test cases are executed manually without using any automated tools. 

* Pros 
  * Does not require programming or automation knowledge
  * Helps to find critical bugs in the application
* Cons
  * It is a time-consuming approach
  * Quality depends on the capabilities of the tester/testing team, the quality of the requirements and the timeframe.
  * Usually, all test cases cannot be covered because of the size of the application or the timeframe.

**Record and Replay** testing is a type of software testing in which a human record set of actions with automation tools and later on, these steps can be reproduced. Future runs can use various data sets for test cases.

* Pros
  * Does not require programming and automation knowledge
  * Can be used as a transition tool from manual to automation testing approach
  * Can be used as an educational tool for learning the testing framework
  * Can be used as a tool for generating test cases before refactoring internal implementations
* Cons
  * Recorded test cases can be broken after minor changes in the application’s behavior, and often test cases should be recorded from the very beginning
  * Recorded test cases can be broken after network speed changes because such tools usually record a “waiting time”
  * Sometimes such tools generate unreadable and unmaintainable code, like Espresso Test Recorder

**Model-based testing** is a type of software testing in which a model of the software product will be created initially. The model is a description of system behavior. Usually, such models help to fully understand an application or feature that simplifies creating efficient test cases that can be automated.

* Pros
  * Allows creating highly efficient test cases
  * Helps achieve high test coverage
* Cons
  * Requires programming skills
  * It requires more time to implement the test suite
  * The detailed model should be created before creating test cases


