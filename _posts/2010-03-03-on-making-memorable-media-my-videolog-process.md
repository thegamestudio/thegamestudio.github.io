---
layout: post
title: "On Making Memorable Media: My Videolog Process"
date: 0210-03-03 20:28:00
category: Monolith
tags:
  - process
  - technical
  - videolog
---

_One of our commenters asked me how I made my little videos, and I figured the answer would merit more than another comment. I'm still perfecting my process, so take this post with a grain of salt._

Making videologs is a very fun and rewarding process that usually create more interest than post text and screenshots. The first step is to get the game to a state where whatever is going to be shown looks awesome. The build I used for the first video I released was full of jank bugs and would freak out often; however, I knew what was going on and chose to only show the parts of the game that were bug free. While bugs are often funny and understood by other developers, my target audience is the people who are going to eventually purchase my product, and it's always best to show them something stable and fun.

<!--more-->

Once I know what I'm going to show off, I run through it once to make sure everything works accordingly. From there, I begin to screencap. There are a number of different screen capture software packages available and I've tried many, but I find [Fraps](http://www.fraps.com/) to be the easiest for my to work with (it handles framerate counts, video recording with audio and screenshots). Once in the game, I begin recording with Fraps while I describe the features I want to highlight and play through the demo level. Once I'm finished with that, the movie is _technically_ ready for upload. You'll have an AVI that is around 300MB per minute of footage (at 720p) which can be uploaded to Vimeo or YouTube or wherever; however, I like to take a few more steps to make the video look really polished.

If I'm going to have any video footage (like in my developer interview videos), I a Flip HD. It records at 720p as well, which makes it easy to splice that footage in with gameplay.

After I've created all the raw footage, I use Adobe Premiere to edit the footage, add title banners and subtext, and encode the video to a more compressed format. You can use any video editing tool to tweak your footage, but I've gotten used to Premiere, and I find it to be something that I can work quickly with.

Finally, once the video is ready for export, I run it through Adobe Media Encoder using the H.262 codec to reduce filesize while maintaining quality (a 3 minute video at 720p resolution goes from ~1GB to ~18MB). Again, Adobe Media Encoder is just a tool that I have on hand, but there are many free tools which do the same thing (Noah has had great success with [FFmpeg](http://www.ffmpeg.org/), although it's a bit more... command liney).

Once I've got my final, edited, encoded video (usually an mp4), I just upload it to YouTube, give it a nice description and embed it here.

That's the process and tools I've been using to create my videologs. I hope this helps anyone who is interested in recording some of their own work! Feel free to ask me questions regarding my process in the comments.
