---
layout: default
title: Plugin Architecture
nav_order: 3
---

The plugin serves as a versatile framework, allowing for easy addition of new providers. To do this, explore the `Flow` directory in the plugin's code. The `Flow.h` file is the foundational interface that all flows adhere to. For a practical example, see the `External/AuthorizationFlow` class, which demonstrates OAuth Authorization Code Flow implementation. This modular design means adding a new provider is as simple as creating a new class and defining a few basic properties, similar to the `External/FacebookAuthorizationFlow` class.

The plugin functions by using a universal login node that selects the appropriate implementation based on the config parameter type. This configuration occurs in `UOAuthPP_SubSystem::Login`. To integrate an additional provider, include it in this section.

For assistance with implementing a new provider, feel free to reach out to me on Discord at taigi100.

{: .note }
I'm looking to reorder the parameters in the config object, but I'm uncertain if Unreal Engine allows for this. If you know how to achieve this, I'd appreciate your guidance.