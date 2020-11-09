---
layout: article
title: 'Never use sleep in test code'
description: 'We will explore approaches for replacing a sleep method in test cases.'
permalink:  /:categories/:title/
categories: [good-practices]
author: alex_zhukovich
---
Almost every application performs long-running operations, and automated UI test cases should wait until this operation is finished. Often we should wait in the following scenarios:
* interaction with the back-end
* interaction with the database (especially when we load a lot of data)
* complicated calculations (plan a route to a destination in navigation applications)

Different frameworks provide solutions for such operations. However, you can often find `sleep` operations in test code, which is usually a feature of the language and not one of the testing framework's approaches.

The main problem of such solutions is that the `sleep` method will wait for a certain amount of time, and very often, the long-running operation can finish faster. In this situation, we are wasting a lot of time because of a long timeout in `sleep` operation. When we have many test cases, we can reduce execution a lot by replacing the `sleep` method with an alternative from the testing framework.

Let's take a look at alternatives that we can use for replacing `sleep` methods. Almost all solutions from different frameworks work in the following ways:
* checking condition multiple times until timeout is over
* integrating test framework to application

## Checking condition multiple times until timeout is over
A typical implementation of the wait method appears in different frameworks, like UiAutomator (`wait`), Appium (`waitForElement`), Espresso (custom ![Idling Resource](https://developer.android.com/training/testing/espresso/idling-resource)). This approach's main idea is to check the condition more than once until timeout is over. Let's imagine that we have a `wait` function with a timeout for 3 seconds, and we will check the condition every second. It means that this function can be done after 1, 2, or 3 seconds, and we can save a lot of time if this function takes more than 1 second for many test cases.

## Integrating test framework to application
Sometimes we can face a different approach, when we have to integrate a test framework inside the application. In this case, when the long-running operation starts, we tell the testing framework that the test case should wait. When the process is finished, we provide information to the framework that the test case can be continued — however, the main problem of this approach that our application is connected with a specific test framework. It can complicate migration to a new framework in the future, and you should always synchronize application code with test code.

As you can see, we have more efficient approaches for replacing `sleep` in the test code, and reduce execution time. I recommend you verify conditions multiple times and don't wait until the timeout is over.

Note: Many frameworks already have such functions.

