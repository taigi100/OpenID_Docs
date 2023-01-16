---
layout: default
title: Facebook
parent: Providers
nav_order: 2
---

Facebook implements an API which allows connections using OAuth2.0. They also support a minimal OpenID flow but this isn't currently supported (However, you can still retrieve the client data with an additional HTTP call using the `access_token`).

[Facebook Login](https://developers.facebook.com/docs/facebook-login/overview) contains the neccessary documentation. [Manually Build a Login Flow](https://developers.facebook.com/docs/facebook-login/guides/advanced/manual-flow) describes the flow used by the plugin in greater detail. 

{: .note }
In my personal opinion, Facebook Login is quite customized, therefore make sure to check their documentation in detail!

{: .warning}
Currently, UE doesn't support retriving fragments from the URL, therefore the [external browser](../advanced/external_browser) flow is not supported! Please user the [embedded browser](../advanced/embedded_browser) flow when trying to use Facebook as an identity provider.

## Long-lived tokens

Facebook offers the option to switch a normal `access_token` for a [Long-lived Access Token](https://developers.facebook.com/docs/facebook-login/guides/access-tokens/get-long-lived). This token lasts for about 60 days (the normal one lasts around 1 day by default), therefore this might be a good way to not have the user perform a re-log every time they open the game.