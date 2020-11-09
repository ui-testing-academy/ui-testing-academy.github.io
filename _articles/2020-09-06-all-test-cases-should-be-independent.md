---
layout: post
title: 'All test cases should be independent'
description: 'We will explore why independent tests is a good practice and how to achieve this.'
categories: [ good-practices]
permalink:  /:categories/:title/
author: alex_zhukovich
---

A test case checks that part of the application works according to requirements. When we have a situation where one test case depends on the other one, we may see unexpected behavior in some test cases because of the following reasons:
* test cases may be executed in random sequence; in this case, some test cases could fail because of the incorrect initial state of the application or environment
* failing one test could cause another test to fail too

Many testing frameworks have a way to execute methods before and after the test case. In the case of JUnit 5, we can annotate methods with `@BeforeEach` and `@AfterEach` methods.

```kotlin
class SuperImportantTestSuite {

   @BeforeEach
   fun setUp() {
      // set up data before each test case
   } 

   @Test
   fun importantTestCase() {
      ...
   }


   @Test
   fun superImportantTestCase() {
      ...
   }

   @AfterEach
   fun tearDown() {
      // clean up data after each test case
      clearDatabase()
   }
}
```

Using methods with `@BeforeEach` and `@AfterEach` annotations from JUnit 5, or similar functionalities from other frameworks we can make our test cases independent. So, we can clean up data before or after each test scenario. In this case, every test case will start from the same state. In this example, the `importantTestCase` and the `superImportantTestCase` will start with an empty database.