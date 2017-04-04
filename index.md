---
title: Is It Snappy?
---

# What is response latency?

Has a game, application, or device ever felt laggy to you?  Have you ever witnessed an argument over which text editor was more responsive?

The reason an interactive UI can feel sluggish or laggy is response latency - the time between an input and its corresponding output.  The response latency of the real world is zero.  When you pick up an object, your fingers and the object move in lockstep.

In computers, there is often a subtle but observable delay between the action you take with your fingers and the resulting effect.  Counterintuitively, as computers have gotten faster and more complex, these delays have lengthened.  For example, if you get the opportunity, play with Windows 95 on old, physical hardware.  It is amazingly responsive.  Similarly, an NES on a tube television has almost zero input latency.  This is part of the reason old twitch games are so hard today -- in a typical modern setup, an extra hundred milliseconds or more has been added between your inputs and their effects.

What makes the situation worse is that some people are more sensitive to response latency than others.

Fortunately, we can measure and quantify this latency!  The traditional technique is to simultaneously record the input device and the screen with a high-speed camera.  Counting the frames between input and output gives an objective latency measure.

# iPhones to the rescue!

All iPhones since the iPhone 6 (in addition to the 9.7-inch iPad Pro) have a rear-facing camera that can record at 240 frames per second.  Nearly four milliseconds of precision in our pockets!

*Is It Snappy?* is an iOS app that makes it convenient to use this hardware to record and quantify latency.

Simply record a video of the input and output.  Then precisely mark the frames when the events occurred.  *Is It Snappy?* will then display the time in milliseconds between the two marked frames.

This video demonstrates recording the latency of the NES Classic on a Dell 2007FP LCD monitor.

<div class="video-group">
<div class="video-block">
<div class="video-container">
<span class="caption"></span>
<video controls="true" preload="none" poster="https://s3-us-west-2.amazonaws.com/isitsnappy/posters/nes_classic_demo.jpg" src="https://s3-us-west-2.amazonaws.com/isitsnappy/movies/nes_classic_demo.mp4">
</video>
</div>
</div>
</div>

Now measure your apps and devices and share the results!

<div class="download-badge">
<a href="https://itunes.apple.com/us/app/is-it-snappy/id1219667593?ls=1&amp;mt=8">
<img alt="Download on the App Store" src="/img/Download_on_the_App_Store_Badge_US-UK_135x40.svg" />
</a>
</div>

# Gotchas

It's a bit surprising how noisy the data is.  I could understand 10 ms swings - sometimes it's really hard to tell which 4.2 ms frame contains the button press, even if you strike the button quickly.  But sometimes I'd see 30+ ms swings between captures.  I wonder why that is - input polling lining up just on either side of a frame?  A 60 Hz frame is 16.6 ms after all.  The lesson is to take several captures.

# Wishlist

It would be pretty cool if the app showed microphone power alongside the video frames so you could quantify latency from input to sound too.

# Experience Reports

After releasing *Is It Snappy?*, I walked around my house and measured everything I could think of.  Here are some interesting results.

## NES on CRT

Check out the latency on an original NES and CRT television (Warning: quite a lot of flicker):

<div class="video-group">
<div class="video-block">
<div class="video-container">
<span class="caption"></span>
<video controls="true" preload="none" poster="https://s3-us-west-2.amazonaws.com/isitsnappy/posters/nes_crt_demo.jpg" src="https://s3-us-west-2.amazonaws.com/isitsnappy/movies/nes_crt_demo.mp4">
</video>
</div>
</div>
</div>

Note that you can see the electron beam scanning down the display.  (I assume it looks diagonal due to how the iPhone camera scans.)  The input is recorded on one frame.  The NES spends the next frame processing.  The next time the beam scans down the screen, Mario is in a new position.  The gold standard!  Also, technically this means response latency is higher if Mario is at the bottom of the screen rather than near the top.  :)

On an LCD, as demonstrated with the NES Classic above, you can see the pixels fade in.  If the LCD's pixel response time is in the typical 10ms range, the effect shows up clearly in a 240 Hz video.

## Fluorescent Flicker

On a related note, I tested *Is It Snappy?* on the train I take to work, and I can directly observe the 120 Hz flicker from the fluorescent lighting.  Sometimes the lights on the right side of the train are in phase with the ones on the left, and sometimes not.

## Television Latency

My primary television is a Samsung LN46C650.  I've always been happy with it, but I recently played through some old games and found them to be trickier than I remembered.  Something never felt quite right.  Well, the NES Classic (which already has some [emulation latency](https://byuu.org/articles/latency/)), on my TV, measures at ~170 ms!  On a Dell LCD monitor, the same game measures at 87 ms.  That means my TV adds ~80 ms (even in game mode!), which is consistent with my other measurements and general feeling that games were never responsive.  80 ms is not that bad by itself, but when you add other sources of latency, it quickly becomes unpleasant.  Guess I'm [in the market for a new one](http://www.rtings.com/tv/tests/inputs/input-lag).  :(

I used to play semi-competitive Quake 3, and my typical ping time was in the 50 ms range.  It's absurd that my TV adds more latency than the time it takes for network packets to travel halfway across the country!

## The Curious Case of Mac Keyboards

This one's bizarre: the onboard keyboards on both the 2015 Macbook Pro and Macbook Air have _worse_ latency than an external keyboard.  Plugging in an external wireless keyboard improves response latency by 40 ms.  What are you doing, Apple?

## Text Editors

On my Dell XPS 13 running Windows 10, I measured:

| Editor | Latency |
| -- | -- |
| Notepad | 70.8 ms |
| VS Code | 116.7 ms |
| Atom | 104.2 ms |
| Atom (Haskell) | 129.2 ms |

On the same machine, running Ubuntu, I measured:

| Editor | Latency |
| -- | -- |
| TextEdit | 62.5 ms |
| VS Code | 95.8 ms |
| Atom | 62.5 ms |

Ubuntu latency is better than Windows 10 on this hardware?!  Way to go!

It's interesting that Atom and VS Code really aren't that bad when editing plain text and measuring a single keypress.  It is interesting that Atom's latency gets worse by two frames when Haskell syntax highlighting is enabled.  More testing in realistic situations is warranted here.
