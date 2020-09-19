---
title: 'Separate your tests from the test automation framework'
description: 'We will explore reasons for separating test cases from the test automation framework'
categories: [general, good-practices]
author: alex_zhukovich
---
The testing framework has a significant impact on the test cases in a project because each framework has its own approach for handling similar situations and issues. Even if you are happy with the framework, chances are that you will change it in the future.

One of the main problems of migration from one framework to another is updating many test cases. When the project is big, you may face yourself adjusting many tests, and this may be time-consuming. The solution for the issue is to introduce abstraction and separate test cases from the testing framework.

Let's take a look at an example of a test case with the Espresso framework, which does the following actions:
* Enter email address
* Enter empty password
* Check that the "Password is blank" error message is displayed

```kotlin
@Test
fun shouldDisplayErrorWhenPasswordIsBlank() {
   val email = "test-account@alexzh.com"
   val password = ""

   // enter email
   onView(withId(R.id.emailEditText))
      .perform(replaceText(email))

   // enter password
   onView(withId(R.id.passwordEditText))
      .perform(replaceText(password))

   // press login button
   onView(withId(R.id.loginButton))
      .perform(click())

   // verification of error message
   onView(withText("Password is blank"))
      .check(matches(isDisplayed()))
}
```

So, let’s try to make the code of the test case framework-independent by extracting base operations (enter text, click on the view, etc.) to functions:

```kotlin
fun enterText(viewId: Int, text: String) {
    onView(withId(viewId))
      .perform(replaceText(text))
}

fun clickOnView(viewId: Int) {
    onView(withId(viewId))
      .perform(click())
}

fun hasText(text: String) {
    onView(withText(text))
      .check(matches(isDisplayed()))
}
```

After that, we can update our test case:

```kotlin
@Test
fun shouldDisplayErrorWhenPasswordIsBlank() {
   enterText(R.id.emailEditText, email)
   enterText(R.id.passwordEditText, password)
   clickOnView(R.id.loginButton)
   
   hasText("Password is blank")
}
```

![image](/assets/images/separate-tests-from-test-automation-framework/framework-independence.svg)

Note: We can apply more advanced techniques for separating test code from the testing framework, like the PageObject pattern.

The additional abstraction level allows you to save a lot of time during switching one technology to another one because, in this case, we only need to update the framework-dependent layer, and the test cases will not be subject to changes.