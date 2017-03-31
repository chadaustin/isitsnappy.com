# What is response latency?

Has a game, application, or device ever felt sluggish or laggy to you?  Have you ever argued with someone over which text editor was faster?

The reason an interactive UI can feel sluggish or laggy is response latency - the time between an input and its corresponding output.  The response latency of the real world is zero.  When you pick up an object, your fingers and the object move in lockstep.

In computers, there are often subtle but observable delays between the actions you take with your fingers and the resulting effects.  Counterintuitively, as computers have gotten faster and more complex, these delays have lengthened.  For example, if you get the opportunity, play with Windows 95 on old, physical hardware.  It is amazingly responsive.  Similarly, an NES on a tube television has almost zero input latency.  This is part of the reason old twitch games are so hard today -- in a typical modern setup, an extra hundred milliseconds or more has been added between your inputs and their effects.

What makes the situation worse is that some people are more sensitive to response latency than others.

Fortunately, we can quantify this latency!  The traditional technique is to simultaneously record the input device and the screen with a high-speed camera.  Counting the frames between the input and the output gives an objective measure of input latency.

# iPhones to the rescue!

All iPhones since the iPhone 6 and the 9.7-inch iPad Pro have a rear-facing camera that can record at 240 frames per second.  Nearly four milliseconds of precision in our pockets!

Is It Snappy? is an iOS app that makes it convenient to quantify latency with this hardware.

<div class="video-block">
<span class="caption">Simply record a video of the input and output.</span>

<div class="video-container">
<video controls="true" width="320" height="568" src="https://s3-us-west-2.amazonaws.com/isitsnappy/movies/capture.mp4">
</video>
</div>
</div>

<div class="video-block">
<span class="caption">Then precisely mark the frame when the events occurred.</span>

<div class="video-container">
<video controls="true" width="320" height="568" src="https://s3-us-west-2.amazonaws.com/isitsnappy/movies/mark.mp4">
</video>
</div>
</div>

Is It Snappy? will display the number of frames and milliseconds between the two events.

<div class="download-badge">
<a href="https://itunes.apple.com/us/app/is-it-snappy/id1219667593?ls=1&amp;mt=8">
<img alt="Download on the App Store" src="/img/Download_on_the_App_Store_Badge_US-UK_135x40.svg" />
</a>
</div>

---

After writing Is It Snappy?, I walked around my house and measured everything I could think of.  Here are some interesting results:

aoue
aoeu
aoue

aoeu

aoeu

aoue

