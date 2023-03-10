---
title: General Concepts
layout: default
nav_order: 2
---

## Intro
---

This doc provides a general intro into what OpenID and OAuth2 are, in layman's terms. For details, please check the references for [OAuth2](https://oauth.net/2/) and [OpenID](https://openid.net/developers/specs/).

## OAuth2
---

> OAuth 2.0, which stands for “Open Authorization”, is a standard designed to allow a website or application to access resources hosted by other web apps on behalf of a user. It replaced OAuth 1.0 in 2012 and is now the de facto industry standard for online authorization. OAuth 2.0 provides consented access and restricts actions of what the client app can perform on resources on behalf of the user, without ever sharing the user's credentials. [^1]

This is the technology behind the "Sign in with..." buttons you see on websites today. If implemented, you can allow your users to sign in with Facebook, Google, etc. into your game and then have access to some functionalities provided by them such as user information (name, email, profile picture etc.) and various actions (e.g. share a high score on Facebook). In this document, these platforms will be referred to as OAuth2 providers.

There are multiple flows in the OAuth2 protocol, let's understand a simple one:
1. The user clicks the Login button.
2. Our game, opens a web browser to the page of an OAuth2 Provider with some instructions contained in the URL params
3. The user logins the web page, and grants access to our game.
4. The webpage sends back to the game a string called an `access_token`.

Once this flow is completed, the game can use the `access_token` (by appending it to a request's headers) to access the authorized  resources from the OAuth2 provider via HTTP calls. For example, you can use it to share something on Facebook.

Please note that this access_token expires after a certain amount of time and will become invalid. The methods to refresh it will be explained later. &#128513;.

In order to use an OAuth2 provider, you will need to register your game within its ecosystem. The process may vary depending on the provider, but at the end of it, you will receive a Client ID and Client Secret which will be used to identify your game.

### URL Params

To configure exactly how the flow works and what permissions you ask for, the following params are used (they are embedded in the URL mentioned before as URL params):
- redirect_uri: After the user authorizes the game, the provider needs a way to send back the `access_token` to the game. This is done by having the provider make a request to the `redirect_uri` containing the `access_token` based on `response_mode`.
- response_mode: Controls how the `access_token` is sent back (in the URL, in the body of the request etc.)
- scopes: represents the permissions you are requesting. For example, on Facebook, the scopes `public_profile email` give you access to retrieve the user's public profile information and email.

There are more options available, but these are the important ones for now. &#128513;

## OpenID Connect
---

OpenID Connect (OIDC) builds upon OAuth2 and offers a few additional features such as single sign-on and access to resources in different places. The main thing to remember for now is that, in addition to the `access_token` OIDC also defines an `id_token` which contains various information about the user (depending on scope, e.g. email, username).

### URL Params
- response_type: Usually, to have the provider return both the `access_token` and the `id_token` this needs to be set to `token id_token`

---

[^1]: [What is OAuth 2.0?](https://auth0.com/intro-to-iam/what-is-oauth-2)