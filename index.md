# Is It Snappy?






Has a game, app, or device ever felt sluggish or laggy or unresponsive to you?  Have you ever participated in or observed an argument over whether one text editor is faster than another?

The reason an interactive UI can feel sluggish or laggy is response latency - the time between an input and its corresponding effect on the screen.  The response latency of the real world is zero.  When you pick up an object, your fingers and the object move in lockstep.

In computers, there is frequently a subtle but observable delay between the actions you take with your fingers and the resulting effect.  As computers have gotten faster and more complicated, this delay has gone up.  For example, if you have the chance, play with Windows 95 on old, physical hardware.  It is amazingly responsive.  Similarly, an NES on a tube television has almost zero input latency too.  This is part of the reason old twitch games are so hard today -- in a typical modern setup, an extra 100 ms or more has been added between your inputs and their effects.

What makes the situation worse is that some people are significantly more sensitive to response latency than others.

Fortunately, we can quantify this!  The traditional technique is to use a high-speed camera to simultaneously record the input device and the screen.  Counting the number of frames between the input and the output gives an objective measure of input latency.

All iPhones since the iPhone 6 and the 9.7-inch iPad Pro have a rear-facing camera that can record at 240 frames per second.  Nearly four milliseconds of precision in our pockets!

Is It Snappy? is an iOS app that makes it convenient to quantify latency with this hardware.

Simply record a video of the input and output.

[insert video]

Then precisely mark the frame when the events occurred.

[insert video]

Is It Snappy? will display the number of frames and milliseconds between the two events.

Quantifying response latency ends arguments! :)

<div class="download-badge">
<a href="https://itunes.apple.com/us/app/is-it-snappy/id1219667593?ls=1&amp;mt=8">
<img alt="Download on the App Store" src="/img/Download_on_the_App_Store_Badge_US-UK_135x40.svg" />
</a>
</div>

---

After writing this app, I walked around my house and measured everything I could think of.  Here are some interesting results:
