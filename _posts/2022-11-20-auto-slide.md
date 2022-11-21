---
date: 2022-08-12 18:47:12
layout: post
title: "Auto Slide"
subtitle: A companion for automatically creating presentation media
description: For when you're too lazy to open PowerPoint
image: /assets/img/covers/auto-slide-big.jpg
optimized_image: /assets/img/covers/auto-slide-opt.jpg
category: experiments
tags:
  - web
author: hsaka
paginate: false
---

After building [Auto Story](https://hsaka.github.io/auto-story/) for helping will storytelling, I had the idea of creating a similar tool to aid with slideshow presentations. What if you could simply speak and your presentation slides could automatically be generated with an appropriate graphic? That's the notion behind Auto Slide.

## The Motivation

I'm pretty bad at presentations. The introvert in me freezes my brain while I'm in the middle of speaking, causing me to lose my train of thought. I tend to have to script my presentations out so I know exactly what to say next. The motivation for Auto Slide came from wondering whether my scripts could be automatically parsed and produce a slide deck for me, without requiring my input. In thinking about the idea a bit more, I realized that I didn't need to limit Auto Slide to parsing scripts at all, instead, I could simply do some speech-to-text recognition and build the slides on the fly. This way, natural speech givers could also use Auto Slide as a companion to display graphics based on what they were saying.

![placeholder](/assets/img/blog%20resources/auto-slide/1-speech.jpg "Speech")

## The Build

Since I had recently built Auto Story using similar technology, I was able to use some of the learnings I had gained on that project to build out Auto Slide. I reused the [annyang](https://www.talater.com/annyang/) library for speech-to-text conversion and did some research for a framework that could handle procedurally creating a slideshow. I found out that [RevealJS](https://revealjs.com/) was more than up to the task. The final piece of the build required displaying an appropriate graphic based on the words being spoken. I found two APIs that could help with this: Google's custom image search API for finding static images based on a search term and the [Giphy API](https://developers.giphy.com/) for finding gif animations. 

![placeholder](/assets/img/blog%20resources/auto-slide/2-giphy.jpg "Giphy")

*A Note From The Future: This was before the proliferation of text-to-image AI APIs like [DallE2](https://openai.com/dall-e-2/) and [midjourney](https://www.midjourney.com/). These definitely could be leveraged in a future update of this tool.*

## The Result

This project came together very quickly because I had already done a bunch of research for Auto Story and the remaining pieces were quite straightforward to integrate. You can freely experiment with Auto Slide [here](https://gamepyong.xyz/autoslide). Feedback is always appreciated! 

![placeholder](/assets/img/blog%20resources/auto-slide/3-auto-slide.gif "Auto Slide")