---
layout: default
title: Design of BlockLauncher's entity renderer API
permalink: /designs/bl_renderer_api.html
---

- Community engagement: saw user demand for creation of custom mobs, saw need
- Reference design: desktop edition API
- Usability: 
 - Number of changes needed to port Desktop Edition models over: fewer is better
- Versatility:
 - Types of models that the API can build: more is better
- More versatile but dangerous: giving raw access to model indices
- Less versatile, safer and easier to use: I name each part of the model, users can only access this part
- "fitting in"
 - Does it follow existing idioms? No, but I decided that porting was more important - weighed it more heavily <- without community feedback!
 - Does follow existing idiom of specifying a render type as a number - internally this was implemented quite differently, but kept old system for familiarity
- Community engagement at the beginning: lackluster; their API suggestions did not meet criteria for defining custom boxes, for example
- After the API is released, community felt that it was too unlike existing methods
 - But now that community have a prototype, can suggest meaningful changes
 - will continue to work with the community on this

Community: they identified a need: https://github.com/zhuowei/MCPELauncher/issues/54#issuecomment-37946229

Early feedback: http://www.minecraftforum.net/topic/2466346-modpe-api-design-entity-model-api/

http://www.minecraftforum.net/topic/1675581-blocklauncher-an-android-app-that-patches-minecraft-pe-without-reinstall/page__st__2740#entry30592931 new suggestions

http://www.minecraftforum.net/topic/1675581-blocklauncher-an-android-app-that-patches-minecraft-pe-without-reinstall/page__st__2600#entry30321124