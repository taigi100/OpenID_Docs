---
title: Getting Started
layout: home
nav_order: 1
---

This document serves as documentation for the UE5 OpenID Client Plugin.

Check out the CHANGELOG to see what’s new!

{: .warning }
This is a code plugin which requires good knowledge of the OpenID protocol. The current version 0.4 does NOT support Facebook login as they don’t support the form_post response mode. Facebook support will be added in future versions.

## Version 0.4
Version 0.4 comes with some big changes! The plugin finally supports a proper browser login flow. The new flow, redirects the user to a new tab in the platform’s default browser, where the user performs all the steps necessary for authentication and authorization. Afterwards, the browser returns the recieved credentials (token, id_token) to the game instance.

To achieve this, the following workflow is being used:
```mermaid
sequenceDiagram
    UE Game ->> UE5 OpenID Client: Login
    UE5 OpenID Client ->> Browser: Open Login URL
    UE5 OpenID Client ->>+ UE5 OpenID Client: Start server at localhost#58;serverPort
    Browser ->> EndUser: OpenID Flow
    EndUser ->> Browser: OpenID Flow
    Browser ->> UE5 OpenID Client: Token + ID_Token via http:#47;#47;localhost:serverPort#47;serverCallback
    UE5 OpenID Client ->> UE5 OpenID Client: Stop Server
    deactivate UE5 OpenID Client
    UE5 OpenID Client ->> UE5 OpenID Client: Add Token to all future requests made via HttpModule
    UE5 OpenID Client ->> UE Game: User
```

## Example project
  [OpenID Complex Browser Example](https://github.com/taigi100/OpenID_Complex_Browser_Example)  - Shows how to log into google and call the APIs afterwards, using [VARest](https://www.unrealengine.com/marketplace/en-US/product/varest-plugin).

## Notes
You can manualy clear the webcache by deleting the saved\webcache folder within the project.