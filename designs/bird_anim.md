---
layout: default
title: Bird animation player
permalink: /designs/bird_anim.html
---

- Not really a work of engineering design - it creates problems instead of solving them - but created with an engineering design approach
- Funny snippet of an exploding bird from Pink Floyd's the Wall
- Wanted to make people see the snippet
- Diverge: 
  - Upload to website?
    - Uploaded to Wiki, but only takes GIFS: no audio, and almost immediately reverted
  - Mess with the tester to deploy?
    - Identified possible ways to show picture
- Begin converging
  - Desktop wallpaper? 
    - Made an incredibly low fidelity prototype - me just setting the .gif as wallpaper manually
      - Did not animate
  - Play snippet of video?
    - Copied video to virtual machine, identified a list of programs that could play video
    - Turns out only one is installed: Firefox
    - Advantages over other combinations: 
      - Animation
      - Sound
      - Not easily removed
- So the plan was to play video every once in a while using Firefox
- Goal: not too difficult and not too easy to remove
  - Metric: number of commands required to remove the infection
  - Criteria: closer to ~3 preferred (what I'm comfortable with)
- Goal: not prevent students from completing work
  - Metric: interval between playback
  - Criteria: larger is better
- Goal: force people to watch the video
  - Metric: interval between playback
  - Criteria: smaller is better

- last two goals conflict: had to balance out.
- From high fidelity prototype, decided that 5 minutes allowed enough work to be done between interruptions

- Goal: not easily detectable
  - Metric: number of lines changed in the tester
  - Criteria: less is better
  - Metric: number of "sensitive" lines - lines with obvious obfuscation or obvious calls to run programs
  - Ctiteria: less is better

- Functional decomposition/modularity

1. Download installer
2. Launch installer
3. downloads remaining files
4. prevent duplicate copies from starting
5. setting a timer
6. increasing volume
7. playing video

- Grouped related functionality
- First two parts are started by tester, using a simple system() call - only 6 lines changed, minimized detection by someone reading source
- The installer does 3 and 4, since it has to start the next payload anyways
- Another script is responsible for setting the timer, increasing the volume, and playing the video, since they have to be done everytime video starts
- Finally, step 7 is done separately as it is the only part that needs to run inside Firefox - this part is written as a webpage, unlike other parts which are shell scripts

- Worked on project in reverse so that no dependence on later stages
- Soon had high fidelity prototype - 3-7, at which point can manually launch and tweak timing
- Finally, added 1-2 

- Program worked well, and was, as expected, easily removed (people on Facebook actually did the first two steps, and provided one command to remove the program)