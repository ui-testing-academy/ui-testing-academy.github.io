---
title: 'Naming conventions for test cases'
description: 'We will explore different naming conventions for test cases.'
categories: [ naming]
author: alex_zhukovich
---
A name is an essential part of a test suite and each test scenario. When analyzing test reports, all you see are the names of the test cases. The right name of the test case provides information about the scenario, and often, it's enough information for understanding the main idea.

Many naming conventions can be applied to test cases.

Note: Some runtime environments allow you to use space `" "` as a separator inside test names; in other cases, one of the most popular options is `"_"`. Example:
```
should_showInvalidAuthenticationMessage_when_passwordIsInvalid
// or
should show authentication message when password is invalid
```

Most used naming conventions for test cases:
## Feature which will be tested
```kotlin
success_to_paid_for_order

fail_to_login_if_account_is_invalid

fail_to_apply_invalid_voucher
```
## [Action] [State under test] [Expected behavior]
```kotlin
pay_validAccount_openSuccessScreen

login_invalidAccount_showInvalidUserMessage

addVoucher_invalidVoucher_showInvalidVoucherMessage
```  
## [Action] [Expected behavior] [State under test]
```kotlin
pay_openSuccessScreen_when_AccountIsValid

login_showInvalidUserMessage_when_AccountIsInvalid

addVoucher_showInvalidVoucherMessage_when_VoucherIsInvalid
```  
## Should [Expected behavior] When [State under test]
```kotlin
should_openSuccessScreen_when_userPayWithValidAccount

should_showInvalidUserMessage_when_loginWithInvalidAccount

should_showInvalidVoucherMessage_when_userAddInvalidVoucher
```
## Given [Preconditions] When [State under test] Then [Expected behavior]
```kotlin
given_userIsAuthenticated_when_accountNumberIsValidToPay_then_openSuccessScreen

given_userIsNotAuthenticated_when_invalidAccountToLogin_then_showInvalidVoucherMessage

given_userIsAuthenticated_when_addInvalidVoucher_then_showInvalidVoucherMessage
```  
