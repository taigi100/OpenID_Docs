---
layout: default
title: Embedded Browser
parent: Login Flows
nav_order: 2
---

The embedded browser flow is using the web browser plugin developed by Epic Games. This plugin allows the creation of a web browser inside your game. Therefore, it is possible to use this to perform the OpenID or OAuth2 flows. This is less secure than using the external browser method.

```mermaid
sequenceDiagram
    UE Game ->> UE5 OpenID Client: Login
    UE5 OpenID Client ->> UE5 OpenID Client: Open Login URL in embedded browser
    UE5 OpenID Client ->> EndUser: OpenID Flow
    EndUser ->> UE5 OpenID Client: OpenID Flow
    UE5 OpenID Client ->> UE5 OpenID Client: Retrieve Token + ID_Token from browser URL
    UE5 OpenID Client ->> UE5 OpenID Client: Add Token to all future requests made via HttpModule
    UE5 OpenID Client ->> UE Game: User
    UE Game ->> UE5 OpenID Client: Remove WebBrowser Widget
```

To use this flow, simply call the login method as in the following example. Keep in mind to replace the Clinet ID with the proper value. For more information refer to [providers](../providers/providers). You also need to create an web browser widget containing only an OAuth++ Web Browser.

<iframe src="https://blueprintue.com/render/9_hqms1p/" scrolling="no" allowfullscreen width="100%" height=600></iframe>