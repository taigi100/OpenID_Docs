---
title: Common issues
layout: default
nav_order: 5
---

## General
#### Unable to properly remove `Authorization` header
When utilizing the default functionality of the plugin to add an `Authorization` header to every outgoing request, it can be difficult to remove this header subsequently. This is because UE only provides the option to set default headers, but not to remove them. To circumvent this limitation, it is recommended to manually set the header for each individual outgoing request instead of relying on the plugin. 

## Facebook

#### Request not returning email address
For Facebook, the email address will only be returned if it is confirmed and set as the primary email. By default, test users do not have their email address set as primary, so to retrieve the email address, you will need to login as the test user through the Facebook dashboard.
Once logged in, navigate to the Settings > Contact and set the email as primary. This will ensure that the email address is returned when the plugin is used.
#### Page scrolled to the bottom
When utilizing the embedded browser within Unreal Engine to access Facebook, an issue arises where the page is automatically scrolled to the bottom upon loading. Unfortunately, with the current functionality offered by the embedded web browser, it is not possible to effectively resolve this issue.

