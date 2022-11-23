---
date: 2017-08-03 22:00:56
layout: post
title: "Reward Systems"
subtitle: Keeping Players Hooked
description: Exploring ways to keep players playing
image: /assets/img/covers/reward-big.jpg
optimized_image: /assets/img/covers/reward-opt.jpg
category: experiments
tags:
  - prototyping
  - phaser
author: hsaka
paginate: false
---

Many modern mobile games include reward systems for unlocking content such as new cards, game characters, or items. These systems usually involve spending some sort of in-game currency in exchange for a chance to win something. There are many different types of these systems and every game usually does it a little bit differently. In this post, we will present two different reward systems that can be used in a game.

![placeholder](/assets/img/blog%20resources/reward/1-reward.jpg "Reward")

## Spin The Wheel

One way to implement a reward system is by using a wheel with prize wedges. Most people are familiar with the paradigm from game shows such as Wheel Of Fortune and The Price is Right. The player simply spins the wheel and the segment that it stops on represents the prize that is won. Some systems include a bad wedge that hurts the player instead of rewarding them (the bankrupt segment). 

![placeholder](/assets/img/blog%20resources/reward/2-spin.jpg "Spin")

This system is fairly simple to implement. The wheel is subjected to a random amount of force every time it is spun and this causes it to land on a random wedge when it stops.

Try Spin n Win for yourself [here](http://gamepyong.com/tutorials/wheel/).

## Scratch To Win

Another way to reward players in a game is by using a scratch ticket. In this approach, the player has a chance to win a prize if they can reveal three of the same symbols on their ticket. This is similar to scratch lottery tickets. Unlike the previous system, the player has a much greater chance of walking away empty-handed because it's much harder to win with this approach.

![placeholder](/assets/img/blog%20resources/reward/3-scratch.jpg "Scratch")

To make it as familiar as possible to people who have played physical scratch games, we can incorporate a virtual foil mask that needs to be scratched with a coin to reveal the symbols below.

Try Feeling Lucky [here](http://gamepyong.com/tutorials/feelinglucky/).
