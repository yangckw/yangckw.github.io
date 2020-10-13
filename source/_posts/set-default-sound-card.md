---
title: set_default_sound_card
date: 2020-10-13 18:20:33
tags: ['system', 'linux']
---

**Run:**

> $ pacmd list-cards

To display the index of your cards. For example, my pci sound card is at index 2. The sound profile for analogue output (again as an example) is called "output:analog-stereo".

Then: 
> $ pacmd set-card-profile 2 output:analog-stereo
To set this as the output (give it a try). To make it permanent, edit **/etc/pulse/default.pa** and add:
> $ set-card-profile 2  output:analog-stereo
> $ set-default-sink 2
Restart pulseaudio or reboot to check persistence.
If you want to also set mic(input) defaults
> $ set-card-profile 2  output:analog-stereo+input:analog-stereo
> $ set-default-sink 2

