---
layout: default
title: Google
parent: Providers
nav_order: 1
---

To get started, follow the [Setting up OAuth2.0](https://support.google.com/cloud/answer/6158849?hl=en#zippy=) guide. In our case, we need a Web Client. In the Web Client settings, you need to add "http://localhost:3333/callback" to the `Authorized redirect URIs`. You can use a different URL, but make sure you use the same one in the blueprint when calling the `Login` method.
