---
layout: default
title: Google
parent: Providers
nav_order: 1
---

Google implements an API which allows us to take full advantage of the OpenID Protocol. Here can find the documentation and details of this API: [OpenID Connect](https://developers.google.com/identity/openid-connect/openid-connect) and [Using OAuth 2.0 to Access Google APIs](https://developers.google.com/identity/protocols/oauth2)

The plugin supports using both OAuth2 and OpenID to connect to Google. You can request various permissions by using the [OAuth2 Scopes](https://developers.google.com/identity/protocols/oauth2/scopes).

To get started, follow the [Setting up OAuth2.0](https://support.google.com/cloud/answer/6158849?hl=en#zippy=) guide. In our case, we need a Web Client. In the Web Client settings, you need to add "http://localhost:3333/callback" to the `Authorized redirect URIs`. You can use a different URL, but make sure you use the same one in the blueprint when calling the `Login` method.

{: .warning }
Please note, Google doesn't allow [embedded browser login](https://auth0.com/blog/google-blocks-oauth-requests-from-embedded-browsers/) anymore! Therefore, the only flow available is the [external browser](../advanced/external_browser) flow.