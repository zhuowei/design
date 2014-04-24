---
layout: default
title: Design of BlockLauncher's entity renderer API
permalink: /designs/bl_renderer_api.html
---

I maintain ModPE, which is a modding API for Minecraft PE originally designed by Treebl and implemented in his runtime as well as in BlockLauncher, my application. Building a good API also requires engineering design, as the creation of the Entity Renderer API in ModPE demonstrates.

The first step of engineering design is to identify the problem: in this case, the area to focus came from community engagement. I received [feedback](https://github.com/zhuowei/MCPELauncher/issues/54#issuecomment-37946229) from many mod creators, stating that they would like the ability to create custom monsters in Minecraft PE. I broke down the problem into multiple parts: one would need a way to save custom mobs with the world, a way to control the custom mobs, and, most importantly, a way to specify what the custom monster looks like. I decided to scope down and tackle the last problem first.

I used engineering design strategies by identifying reference designs and metrics. The reference design that I consulted was the mob renderer API from Minecraft Desktop Edition, which has all the features that I planned to add to my renderer API. The metrics I identified were:

- Usability: 
 - Number of changes needed to port Desktop Edition models over: fewer is better
 - Time to learn the API: less is better
- Versatility:
 - Types of models that the API can build: more is better
- "fitting in"
 - Does it follow existing idioms in the ModPE API?

I decided to adopt an API that heavily resembles the Desktop Edition API, but does not look like existing ModPE methods at all, neglicting the last metric. I chose this because I anticipated (without community feedback) that one major use case of the API would be to port models developed for Desktop Edition to the Pocket Edition, and so I assumed that usability in the form of porting fidelity should be weighed heavily. 

When possible, though, I did try to follow existing conventions: each render type can be used like the models built into the game, even though the custom render types were implemented differently, so that less time is needed to familarize oneself with the API.

Details of the API were also weighed against the metrics - such as the method to access each part of the Minecraft model. I had came up with two approaches: one was to give the script direct access to Minecraft's model parts by indexing into an array. This would allow the editing of multiple types of models, making it more versatile, but may cause memory corruption, reducing its usability. The other approach requires me to name each part of the model, and the users would only be able to access the named parts. This limits its use to parts that have been given names, but avoids the crashes caused by accessing invalid indices. In the end, I decided that versatility in this case is second to usability, and thus chose the safer second method.

In the end, the high fidelity prototype of API fulfilled what I considered to be the objectives of the project: as I demonstrated [here](http://www.minecraftforum.net/topic/1675581-blocklauncher-an-android-app-that-patches-minecraft-pe-without-reinstall/page__st__2600#entry30321124), Desktop Edition models could be ported in an easy 3-step process. However, this doesn't mean that the prototype is perfect: far from it.

After the API released, the community felt that, while the API was not difficult to learn, it was too unlike existing methods. I also observed that, contrary to my assumptions, most models were not ports from Desktop Edition, but were original creations, meaning that desktop edition compatibility shouldn't have been weighed as heavily. Based on these feedback, I am planning to re-iterate and create better APIs based on community suggestions, such as [this more ModPE like alternative](http://www.minecraftforum.net/topic/1675581-blocklauncher-an-android-app-that-patches-minecraft-pe-without-reinstall/page__st__2740#entry30592931).

During the project, I noted that the community is most likely to give useful advice with a high fidelity prototype. The prototype seems to indicate the purpose of the API, and so the suggestions were in the same scope. In contrast, at the beginning of the project, the feedback I received were often [irrelevant](http://www.minecraftforum.net/topic/2466346-modpe-api-design-entity-model-api/) because posters misunderstood the purpose of the API.