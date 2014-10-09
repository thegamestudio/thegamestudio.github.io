---
layout: post
title: "Forward Thinking and Content Generation"
date: 2010-03-01 06:50:00
category: Monolith
tags:
  - developer commentary
  - editor
  - math
  - technical
---

One of the biggest problems when working on a game (or any project that is constantly changing) is trying to predict the future.  From the start, we knew we wanted to have multiple maps with different layouts in each; however, upon implementation, many unknowns appeared. Will we ever change gravity on a map? What about the map radius? How about friction, lighting, run speed, jump height... the list continues <em>ad nauseum</em>.

As a developer, I've got to constantly ask these questions (and often times, come up with my own answers). While working on the map editor, one question came up that had never really been addressed before: Will our towers have different radii? The official answer: "I dunno'." The programmer's answer: "They can."

<em>Warning: The following post contains math. To make up for it, I've also included screenshots with captions consisting of mostly smaller words.</em>

<em><strong>Edited: The final bit of math is now actual math and not made up wrong math.</strong></em>

<!--more-->

![An average-sized tower.][average-tower]

The new map editor will allow a level designer to specify any height and width (although, if you put in crazy numbers, the game will just crash), and the game will dynamically determine the proper radius to make the tower look right. The radius is calculated with a bit of clever math, but it can handle map sizes from very small to very, game-breakingly large.

![Woah, that's a big tower!][large-tower]

An arc-length can be defined by the following equation:

<img title="\200dpi \theta = \frac{s}{r}" src="http://latex.codecogs.com/png.latex?\200dpi \theta = \frac{s}{r}" alt="">

This states that any angle can be represented as an arc-length divided by a radius. Since the arc-length of each block is a constant (each tile has a fixed size of 96x96 pixels), I needed to determine what the proper angle was for the radius of the tower to look right.

The angle could be determined by dividing the total radians in a circle by the number of tiles in a tower map, w, giving us the following equation:

<img title="\200dpi \theta = \frac{2\pi}{w}" src="http://latex.codecogs.com/png.latex?\200dpi \theta = \frac{2\pi}{w}" alt="">

Now that the angle-per-tile for the map is calculated, the radius can be determined with the following equation:</p>

<img title="\200dpi r = \frac{s}{\theta} = \frac{s w}{2\pi}" src="http://latex.codecogs.com/png.latex?\200dpi r = \frac{s}{\theta} = \frac{s w}{2\pi}" alt="">

![A cute, little tower.][small-tower]

Once the math was applied, varying the tower's radius was as simple as changing the width of the tower's map. This allows level designers to jump in and create towers of any height and width without worrying about any of that math business.

When I began work today, I never expected to solve this problem. Not that I thought I couldn't solve the problem, I just never imagined that the problem would arise; however, by using forward thinking and tackling this problem before it actually came up six months later ("Hey Zach, can our towers have... <em>different widths</em>?"), I was able to implement a solution without having to do much integration later in the development cycle.

[average-tower]: https://s3.amazonaws.com/thegamestudio/web/2010-03-01-forward-thinking-and-content-generation-average-tower.png "Average-sized tower"
[large-tower]: https://s3.amazonaws.com/thegamestudio/web/2010-03-01-forward-thinking-and-content-generation-large-tower.png "Large tower"
[small-tower]: https://s3.amazonaws.com/thegamestudio/web/2010-03-01-forward-thinking-and-content-generation-small-tower.png "Small tower"
