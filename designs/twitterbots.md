---
layout: default
title: Twitter bots
permalink: /designs/twitterbots.html
---

- Exercise in: adapting existing code
 - Time to market: don't need to handle irrelevant parts of the Twitter api myself
 - Resiliance: If Twitter API changes, I only need to update the library and not my code

- First two bots: comparison bots
- Functional decomposition
 - Load tweets
 - Extract word/adjective pairs
 - Find adjectives with more than two nouns/nouns with more than two adjectives
 - Generate message containing a random adjective/noun from this list
 - Post tweets with said message
- The first three parts:
 - Takes a long time
 - only needs to be done once
- So separate into two stages: preprocess archive and then have a lightweight bot that only runs the last steps
- No reference design for word pairs: researched solutions with similar aim: grammar checkers -> link grammar
- Wrote a Java program to extract
- Bot: reference design: Misp's twitter_ebooks bots
- Bot is written in simple Ruby based on example bot

- Second two bots: image processing bots
- Again, fn. decomp for modularity
- Listens for pictures sent to account
- Detect face and Add images based on face detection result
- Send new picture as a reply
- Reference design: Android's face detection ability
- Found a port of Android's library to normal Linux
- Fn. Decomp lets me work on this part separately from the bot that listens to replies
- Before bot part was done, to build a medium-fidelity prototype, wrote a script that loads files from local hard drive into image generator so I can easily tweak image positions
- when done, integrate work with twitter bot
- When adding new bot, realized that bot was not modular enough: 
  - detect face - doesn't change; add images - changes
- Refactored code to separate face detection and overlay logic for reuse
 - Iteration