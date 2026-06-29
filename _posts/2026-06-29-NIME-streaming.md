---
title: 'Livestreaming the NIME 2026 Conference'
date: 2026-06-29
permalink: /posts/2026/06/nime-streaming/
tags:
  - conference
  - research
  - chi
---

This June, [our lab](https://instrumentslab.org/) co-hosted the [New Interfaces for Musical Expression](https://nime2026.org/) conference at Loughborough University London.

Jordie Shier and I were the Hybid Chairs for this conference, livestreaming paper presentation sessions (dual tracks) from 9am to 5pm each day and concerts from 7pm - 11pm across 2 venue spaces over at [Rich Mix](https://richmix.org.uk/).

Below is an overview of the streaming setups that we used. This shouldn't necessarily be seen as a perfect guide to livestreaming a conference (there's definitely room for improvement!) but in the preparation for this conference I found other guides (such as [Charles Martin's Hybrid Conference setup](https://charlesmartin.au/blog/2023/07/20/hybrid-conference)) very useful to reference.

For all of the streaming, we used [OBS](https://obsproject.com/) to stream to YouTube.

Papers Track
======
This was the first time that NIME was a dual track conference, meaning that we needed to facilitate 2 simultaneous livestreams.

Each setup was similar (though with a different model of vision mixer in each room due to what we had available). In each room, we had the following requirements:

- HDMI from presenter's laptop going to projector and livestream
- Audio from either HDMI or 3.5mm analogue stereo jack going to room speaker and livestream
- Camera showing presenter
- Wireless microphones going to room and livestream
- Remote presenters able to present over Zoom (and hear questions from the wireless mics in the room)
- Video playback of pre-recorded remote presentations when required

The rooms had HDMI inputs for the projector but no analog audio inputs, meaning that we needed to use the vision mixers to embed the analogue audio into the HDMI feed. If we hadn't needed analogue audio input, a cheaper option may have been an HDMI capture card with an HDMI through to feed the projector.

We used a [Blackmagic ATEM Mini Pro](https://www.blackmagicdesign.com/uk/products/atemmini) vision mixer in one room and a Roland V-8HD vision mixer (with a [Rode HDMI Capture Card](https://rode.com/en-gb/products/hdmi-usb-c-converter)) in the other. With each vision mixer, HDMI input 1 was the presenter's laptop and HDMI 2 was the streaming laptop. Both had a 3.5mm stereo line in running into the analog audio input.

The [Sennheiser Speechline](https://www.sennheiser.com/en-gb/product-families/speechline-wireless) microphones installed in the room went to the PA, we took splits of the outputs of these receivers into an audio interface.

We used a USB webcam to cover the presenter.


In OBS, we took in the audio from the audio interface (the wireless mics) as well as the audio from the vision mixer feed (the HDMI and 3.5mm jack audio). For video, we took in the vision mixer feed (containing either the presenter HDMI feed or streaming laptop HDMI feed for Zoom and video playback).

To have remote presentations over Zoom, we needed a way for them to hear the wireless mics without hearing an echo of themselves (effectively provide a mix-minus feed). This is where having the audio interface for mics and vision mixer for presentation audio came in handy - we could use the audio interface as the input to Zoom and the HDMI as the output for Zoom audio. This meant that the Zoom presenter didn't hear themselves, but their audio still went to the room and to the stream (via the vision mixer).

All this is probably a little clearer in the diagram below, hastily drawn in powerpoint (sorry).




Evening Concerts
======

The evening concerts were in two different venues within Rich Mix. As there was generally only 10-20 minutes break to move between the venues (with one on the 4th floor and the other on the ground floor), we effectively required two separate streaming rigs again. 

For audio, the Rich Mix technicians kindly provided us a stereo feed of the front-of-house mix in each room and we also had a Zoom H1N mounted to a camera in the back of each room (using it as a USB audio interface to function as a stereo room mic).

For video, we borrowed two JVC GY-HM600 video cameras (one for each room). These have a clean HDMI output (no information overlays) that went into a [Rode HDMI Capture Card](https://rode.com/en-gb/products/hdmi-usb-c-converter). We also used smartphones for additional angles. Generally, we had one for a wide shot at the back of the room (using either Apple's continuity camera or [vdo.ninja](https://vdo.ninja/) to get the feed into OBS) and an additional smartphone being operated handheld close to the stage for an additional angle, again using [vdo.ninja](https://vdo.ninja/).

Finally, though we didn't take the feed into the streaming computer, we gave the stage managers a GoPro mounted on a microphone stand to use in each room. The HDMI output of this was displayed on the projector for some of the performances - which hopefully gave the audience a better view of some of the more subtle interactions onstage.

We had a laptop at the back of each room, with the various video and audio feeds for each room going into that laptop, running OBS. We wanted one continuous stream for the entire evening which presented a problem when the stream between laptops. Luckily, Jordie discovered that YouTube primary and backup stream URLs can be used for this purpose. We started one laptop streaming to the primary server then, when we switched rooms, we would start streaming in the other room to the backup server and stop the stream in the first room. This ensured that the stream remained uninterrupted.

