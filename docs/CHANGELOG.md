---
title: CHANGELOG
layout: default
nav_order: 3
---

# Version 0.4 - Major changes

## New features:
  - Added OpenID_Client_SubSystem
  - Now plugin using the OS provided browser to do the login flow within the OpenID_Client_SubSystem
  - Various small refactorings

## Removed:
  - UE4's internal browser flow.

# Version 0.3

Various quality of life improvments.

## New features:
  - Provide facebook / google apps for testing.
  - Added `params` parameter to methods that open a browser in order to be able to pass custom x-www-form-urlencoded query params.
  - Add methods to do the full login/logout process within one single node.

## Bug fixes:
  - Fix various bugs regarding browser oauth2 to google or facebook.

## Example projects:
  - Create three projects to demonstrate each use-case separately.


# Version 0.2

## New Features:
- Add support for implicit flow

## New Classes:
### UOpenID_WebBrowser
- Extension of UWebBrowser
- Provides default behaviour for implicit flow

## Example project:
- Add implicit flow example