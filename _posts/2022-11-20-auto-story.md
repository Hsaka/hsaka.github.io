---
date: 2022-08-10 12:17:22
layout: post
title: "Auto Story"
subtitle: A tool for interactive story-telling
description: Making story-telling fun again
image: /assets/img/covers/auto-story-big.jpg
optimized_image: /assets/img/covers/auto-story-opt.jpg
category: experiments
tags:
  - phaser
author: hsaka
paginate: false
---

One of the things that every software developer at [Teleios Systems Limited](https://www.teleios-systems.com/) is called upon to do is prepare something that interests them and present it to the wider company during a Friday event dubbed *Power Hour*. It's a chance to do some research and build something that's not necessarily related to your everyday development work.

![placeholder](/assets/img/blog%20resources/auto-story/1-power-hour.jpg "Power Hour")

For one of my previous Power Hour showcases, I wanted to explore a more interactive way of telling stories. It was an idea that I had in the back of my mind for a while and I figured that Power Hour was the ideal event to bring the idea to life.

## The Motivation

As a child, I've always loved reading books and listening to stories. The motivation for building Auto Story stemmed from wanting to provide a way for parents/guardians/storytellers to be able to keep their kids/listeners engaged with the stories they are narrating. At the time of building, I did not have any kids of my own but I could imagine what it would be like to tell a story to my child and have that story magically come to life for the purposes of inspiring wonder and stimulating imaginations. With this motivation in mind, I set about building out the idea.

![placeholder](/assets/img/blog%20resources/auto-story/2-storyteller.jpg "Storyteller")

## The Build

For making this idea into a reality, I turned to my trusty game development skills, and, in particular, to the [Phaser](http://phaser.io/) game framework. I knew from the start that I wanted a low barrier to entry with this application and a web-based app can't be beaten when it comes to distribution. As with all of the tools that I make, the first step is to find out what open source projects can be leveraged to quickly aid with development. First, I needed a way to do speech-to-text conversions. For that, I used a library called [annyang](https://www.talater.com/annyang/), which relies on Google Chrome's speech-to-text capabilities. Some quick prototyping with the library proved that it was up to the task. 

Next, it was necessary to generate animated objects based on the text being narrated in the story. I remembered that Google released an interesting drawing recognition game called [Quick Draw](https://quickdraw.withgoogle.com/) some time ago. This game required the user to draw the given prompt within a time limit. I wondered whether the dataset for Quick Draw was available to be used, and luckily enough, they provided it [here](https://github.com/googlecreativelab/quickdraw-dataset)! This dataset contained a ton of drawings that I could leverage within Auto Story, and that's exactly what I did.

![placeholder](/assets/img/blog%20resources/auto-story/3-quick-draw.jpg "Quick Draw")

So now I was able to grab the text from the story that the user was narrating and find matching drawings in the Quick Draw dataset for populating the story's scene. I wanted to go a little deeper with this and make it possible to do some simple manipulations of the objects in the scene. For instance, if the user asks for a green frog, Auto Story should colour the frog in the Quick Draw dataset (which is devoid of colour), green. I did this by making use of another library called [Rough.js](https://roughjs.com/), which fills shapes with a hand-shaded effect. Another manipulation that I wanted to support was the ability to describe the size of an object. Objects should scale based on the size adjective that the user chooses to attach to the object (small, big, tiny, huge, etc.) Finally, I wanted to add the option for the narrator to give objects a name and then be able to refer to that object by its name later on. This would allow you to say something like "There was a dog named Rusty", and then later say "Rusty was brown in colour" to change the dog's colour.

After implementing all of the features described above, I found that the objects populating the story were a bit lifeless, so I decided to add some subtle animation to them. I wanted to apply a style of animation commonly seen in older cartoons, where the lines tend to jump around slightly from frame to frame giving a more pronounced hand-drawn effect. To achieve this, I used the Rough.js library to generate several different frames of a drawing, where each frame has a slightly different outline than the others. When these frames are combined into an animation, it looks as if the objects are constantly moving.

![placeholder](/assets/img/blog%20resources/auto-story/4-rough.jpg "Rough JS")

In addition to spawning characters and objects into the scene, I wanted to also support being able to change the background based on what is being narrated. I added several different background types for keywords like "ocean" and "dungeon". There aren't very many backgrounds provided, but this is an area that could use some AI-generated images in the future.

## Doodle Maker

The Quick Draw dataset contains many drawings, but it doesn't have everything. To support custom keywords, I added the Doodle Maker. This tool allows you to draw a doodle and give it an associated keyword so that when the keyword is referenced in a story, the corresponding doodle appears. This allows the user to add personalized characters or objects to their stories.

![placeholder](/assets/img/blog%20resources/auto-story/5-doodle-maker.jpg "Doodle Maker")

## Exporting

With all of these features in place, a complete story could be narrated and generated. The final element was to allow the user to export their story for sharing or printing. I wanted to be able to support sharing a link to your generated story and exporting the story as a gif animation as well as a PDF document. For the PDF, I used the [PDFMake](http://pdfmake.org/) library and for gif animations, I used [gif.js](https://jnordberg.github.io/gif.js/). Both were fairly straightforward to wire up into the project.

## The Result

I presented Auto Story for my Power Hour showcase segment, and it was very well received. It's currently freely available to try out [here](https://gamepyong.xyz/autostory/). I intend to use it for my own storytelling adventures with my son in the future.

![placeholder](/assets/img/blog%20resources/auto-story/6-auto-story.jpg "Auto Story")