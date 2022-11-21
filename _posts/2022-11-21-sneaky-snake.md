---
date: 2022-11-21 18:34:33
layout: post
title: "Sneaky Snake"
subtitle: Get up and move to control your Snake's movement
description: Your body is the controller in this unique take on classic Snake
image: /assets/img/covers/sneaky-snake-big.jpg
optimized_image: /assets/img/covers/sneaky-snake-opt.jpg
category: gamedev
tags:
  - phaser
author: hsaka
paginate: false
---

An idea I've had for a while was to blend the physical world with games in some way. What if your motion in the real world affected your character's motion in a game? That was the essence behind Sneaky Snake; a twist on the classic Snake game where your physical movements control the in-game snake.

![placeholder](/assets/img/blog%20resources/sneaky-snake/1-game.jpg "Game")

## The Build

Having recently completed building another Snake variant, [Snake 99](https://hsaka.github.io/snake-99/), I was able to reuse a lot of the Snake code from that game in this one. In fact, most of the sprites were also reused. The one addition to Snake that I added was the inclusion of enemies that move around randomly and hurt the player if hit. The core feature that needed to be built was the ability to detect the player's motion. For that, I relied on the browser's gyroscope and accelerometer APIs, specifically these listeners:

```js
if (window.DeviceOrientationEvent) {
     window.addEventListener(
        'deviceorientation',
        this.deviceOrientationHandler.bind(this)
     );
}

if (window.DeviceMotionEvent) {
    window.addEventListener(
        'devicemotion',
        this.deviceMotionHandler.bind(this)
    );
}
```

The device orientation handlers are responsible for detecting when a change in the device's physical orientation happens, and then determine which direction and how much to rotate the snake. The device motion handlers react to the user's motion and use that to actually move the snake.

I also wanted the game to react when the user does not move and translate that into an invulnerability status for the player. If the user stops moving, the Snake turns into stone and cannot be hurt by enemies. The objective was to grow and survive for as long as possible.

![placeholder](/assets/img/blog%20resources/sneaky-snake/2-game.jpg "Game")

## The Result

I used this game in a presentation at work about the possibilities of the gyroscope and accelerometer APIs in modern mobile browsers. Co-workers loaded the game on their phones and were walking around all day trying to get high scores. You can walk around to control your snake as well with the free game on itch.io [here](https://hsaka.itch.io/sneaky-snake).

![placeholder](/assets/img/blog%20resources/sneaky-snake/3-title.jpg "Title")