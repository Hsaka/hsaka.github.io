---
date: 2017-06-02 05:54:56
layout: post
title: "Marble Pitch"
subtitle: Knuckle Down and Get Rolling
description: Building one of the oldest games in the world
image: /assets/img/covers/marbles-big.jpg
optimized_image: /assets/img/covers/marbles-opt.jpg
category: gamedev
tags:
  - caribgames
  - phaser
author: hsaka
paginate: false
---

Playing with marbles is one of the oldest and most pervasive games in the world. Made of clay, stone, ceramic or glass, marbles are small spheres about half an inch in diameter; though some like the 'Big-Goonks' are a bit larger. Modern marbles usually contain a swirl of coloured glass inside. In Trinidad, the most coveted marbles were usually crystals (coloured glass with nothing inside), 'K-K' (opaque white marbles with coloured designs), 'Snake Eyes' (marbles that contained 2 or 3 dark swirls) and the aforementioned 'Big-Goonks' (larger and heavier than regular marbles).

![placeholder](/assets/img/blog%20resources/marbles/1-marbles.jpg "Marbles")

There are many different games that can be played with marbles. Every country seems to have their unique variants of the traditional game. The most common game and the one used by most countries for tournament play is known as 'Ringers' (or Rings in Trinidad). Several marbles are scattered in a ring and players take turns trying to hit them out of the ring using their own marbles. In Trinidad and Tobago, there are a few traditional marble games including 3-hole (where 3 holes are dug equidistant from each other and players compete to be the first ones to pitch a marble into each subsequent hole) and 'Digs-een digs-out' (in which a player pitches/'digs-een' a marble into a hole and others try to get the marble out of the hole or 'digs-it-out')

![placeholder](/assets/img/blog%20resources/marbles/2-marbles.gif "Marbles")

## The Build

We concentrated our efforts on recreating the game 'Ringers'/'Rings'. In this game, 13 marbles are placed into the pot and players try to knock them out. The player who reaches 7 marbles first is the winner. We built this as a 2 player, local multiplayer game in which both players play on the same browser and take turns using the mouse to pitch. For this recreation, we amended the rules a bit such that the turns alternate even if a player has knocked out a marble from the ring.

This game was built using HTML5 technology with the [Phaser](http://phaser.io/) game framework. It uses [P2 physics](https://github.com/schteppe/p2.js) to achieve the marble interactions. Below we will go into the technical details of building the game.

A while back, the creator of Phaser, [Richard Davey](https://twitter.com/photonstorm) wrote an awesome e-book ([Interphase #1](https://phaser.io/interphase)) which included several sample games built using Phaser. We borrowed heavily from the 8-ball Pool sample game included in Interphase for our game because, if you think about it, pitching marbles and playing pool are pretty similar when it comes down to the physics involved.

The first step we took was to setup the physics system for the game. Phaser has two different types of physics systems built into it: Arcade Physics and P2 Physics. For this game, we use the P2 physics system because it allows us to model the interactions between marbles pretty well. We created several physics bodies for objects in the game such as the bounding wall (the court), the ring and, of course, all of the marbles. If we turn on physics debugging mode, you can see the physics bodies below:

![placeholder](/assets/img/blog%20resources/marbles/3-marbles.jpg "Marbles")

When marbles hit the court bounds, they rebound, losing some of their velocity as they do. The inner ring bound is used to constrain the marbles into the ring at the start of the game (the ring is the white square between the ring-out sensor and the ring bounds above). The ring itself is a square instead of a circle for convenience purposes; it allows us to use a square sensor to detect when marbles have left the ring. This inner ring is only alive for three seconds before the game starts to prevent marbles from rolling out of the ring and then it is removed to allow marbles to pass freely. The ring-out sensor does not impart a physical force when marbles collide with it but it is very important as it detects when marbles have been knocked out of the ring.

The players' marbles (white) are positioned at opposite ends of the court at the start of the game. The hand pointer reacts to mouse movements; it rotates around the player's marble as you move the mouse. This indicates the direction that the marble will travel in. The power bar also reacts to the mouse and indicates the strength of the force that will be applied to the marble. When a marble from within the ring collides with a player's marble, it remembers which marble it was struck by. This allows us to know which player won that marble when it moves out of the ring.

That's pretty much it. The first player to knock out 7 or more marbles from the ring is the winner. The final game can be seen below:

![placeholder](/assets/img/blog%20resources/marbles/4-marbles.jpg "Marbles")

You can play the game here: [Play Pitch](http://gamepyong.com/pitch/)