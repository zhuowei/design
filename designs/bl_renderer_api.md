---
layout: default
title: Design of BlockLauncher's entity renderer API
permalink: /designs/bl_renderer_api.html
---

I maintain ModPE, a modding API for the video game Minecraft PE. Building a good API also requires engineering design, as the creation of the Entity Renderer API in ModPE demonstrates.

The first step of engineering design is to identify the problem. Through community engagement, I received [feedback](https://github.com/zhuowei/MCPELauncher/issues/54#issuecomment-37946229) from mod creators, stating that they would like to create custom monsters. I broke down the problem into multiple parts: saving custom mobs with the world, controlling custom mobs, and, most importantly, specifying the apperance of custom monsters. I decided to scope down and tackle the last problem.

I used engineering design strategies by identifying reference designs and metrics. I consulted the mob renderer API from Minecraft Desktop Edition, which has all the features that I planned to add to my renderer API. The metrics I identified were:

- Usability: 
 - Number of changes needed to port Desktop Edition models over: fewer is better
 - Time to learn the API: less is better
- Versatility:
 - Types of models that the API can build: more is better
- "fitting in"
 - Does it follow existing idioms in the ModPE API?

I decided to adopt an API that heavily resembles the Desktop Edition API, but does not resemble existing ModPE methods, neglicting the last metric. I chose this because I anticipated (without community feedback) that one major use case would be adapting Desktop Edition models to the Pocket Edition, and so I assumed that porting fidelity should be weighed heavily. 

When possible, though, I did try to follow existing conventions: custom models can be used like the models built into the game, even though they were implemented differently, so that less time is needed to familarize oneself with the API.

Details, such as the method to access parts of the model, were also evaluated with metrics. I had two approaches: one was to give the script direct access to the model parts by indexing into an array. This would allow the editing of multiple types of models, making it more versatile, but may cause memory corruption, reducing its usability. The other approach requires me to name each part of the model, and the users would only be able to access the named parts. This limits its use to parts that have been given names, but avoids the crashes caused by accessing invalid indices. In the end, I decided that versatility in this case is second to usability, and thus chose the safer second method.

In the end, the high fidelity prototype of API fulfilled what I considered to be the objectives of the project: as I demonstrated [here](http://www.minecraftforum.net/topic/1675581-blocklauncher-an-android-app-that-patches-minecraft-pe-without-reinstall/page__st__2600#entry30321124), Desktop Edition models could be ported in an easy 3-step process. However, this doesn't mean that the prototype is perfect: far from it.

After the API released, the community felt that, while the API was not difficult to learn, it was too unlike existing methods. I also observed that, contrary to my assumptions, most models were not ports from Desktop Edition, but were original creations, meaning that desktop edition compatibility shouldn't have been weighed as heavily. Based on these feedback, I am planning to re-iterate and create better APIs based on community suggestions, such as [this more ModPE like alternative](http://www.minecraftforum.net/topic/1675581-blocklauncher-an-android-app-that-patches-minecraft-pe-without-reinstall/page__st__2740#entry30592931).

During the project, I noted that the community gives more useful advice with a high fidelity prototype. The prototype indicates the purpose of the API, and so the suggestions were in the same scope. Without the prototype, the feedback I received were often [irrelevant](http://www.minecraftforum.net/topic/2466346-modpe-api-design-entity-model-api/).