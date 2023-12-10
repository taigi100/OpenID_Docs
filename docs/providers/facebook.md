---
layout: default
title: Facebook
parent: Providers
nav_order: 2
---

[Facebook Login](https://developers.facebook.com/docs/facebook-login/overview) contains the neccessary documentation. [Manually Build a Login Flow](https://developers.facebook.com/docs/facebook-login/guides/advanced/manual-flow) describes the flow used by the plugin in greater detail. 

## Long-lived tokens

Facebook offers the option to switch a normal `access_token` for a [Long-lived Access Token](https://developers.facebook.com/docs/facebook-login/guides/access-tokens/get-long-lived). This token lasts for about 60 days (the normal one lasts around 1 day by default), therefore this might be a good way to not have the user perform a re-log every time they open the game.