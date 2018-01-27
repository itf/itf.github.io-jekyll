---
title: Multi-audio (In development)
tag: [Projects, Audio]
math: true
summary: Like multi-monitor, but for audio. Using zita convolver, jack and qt.
---

I enjoy [binaural](https://en.wikipedia.org/wiki/Binaural_recording) audio. If you don't know what I'm talking about, I'd recommend putting on headphones and listening to the [virtual barber shop](https://www.youtube.com/watch?v=IUDTlvagjJA).

## What makes audio binaural?

In few words, you can detect from which location a sound is coming from by detecting the delay (difference in phase)   between the ears, which can reach $\frac{25cm}{330m/s} \approx 0.8ms$. However, we can localize the source of a sound in 3 dimensions and the difference in phase only provides us with one constraint. The rest of the information comes from how frequencies are absorbed by the head, outer ear and body are direction dependent; as well as the difference in audio intensity between the ears. 

## Programs that use HRTF
The response of each ear based on the direction of the sound is called [Head-related transfer function (hrtf)](https://en.wikipedia.org/wiki/Head-related_transfer_function). Multiple programs can make use of HRTF in order to localize a sound source. Games that use [openal](https://www.openal.org/) usually have a setting to activate HRTF if you are using headphones. One example of such game is Minecraft. Another program is [pulseaudio](https://www.reddit.com/r/linux_gaming/comments/2ot5ov/enable_system_wide_hrtf_with_pulseaudio/). It allows you to convert 5.1 audio into binaural audio by localizing the sound that would come from each of the speakers. This makes watching movies with a headphone a fairly pleasing experience.

## Basic idea

It is easy to set up audio pipes using jack. I usually install [Cadence](http://kxstudio.linuxaudio.org/Applications:Cadence) to do so, since it is extremely user friendly. Therefore, if I can setup a simple jack application that uses a simple GUI to decide the location of an audio source and then play the audio on headphones, it should allow me to do things such as multiaudio or having some sound sound like it is moving around me.

## Implementing

