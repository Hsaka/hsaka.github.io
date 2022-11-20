---
date: 2022-11-19 03:38:22
layout: post
title: "Going with Godot"
subtitle: How a completely free and open source game engine beats the rest
description: The start of a gamedev journey with Godot
image: /assets/img/covers/going-with-godot-big.jpg
optimized_image: /assets/img/covers/going-with-godot-opt.jpg
category: gamedev
tags: 
  - godot
author: hsaka
paginate: false
---

I've used a bunch of game engines and libraries in my time as an indie game developer. From the now abandoned [Pulpcore](https://code.google.com/archive/p/pulpcore/) for Java Applets back in 2009 all the way up to [Unity](https://unity.com/) and [Unreal Engine 5](https://www.unrealengine.com/) in 2022, I've tried to keep up-to-date with the progression of game engine releases over the years.

At the start of November 2022, the [GitHub Game Off 2022 Game Jam](https://github.blog/2022-11-01-game-off-2022-theme-announcement/) was kicked off and I decided to partner up with a friend to make an entry for it. He had a lot of experience using [Godot](https://godotengine.org/) and Unity, while I was primarily using [Phaser](https://phaser.io/) at that time. I had been hearing very good things about the Godot engine for a while but never really had the time to try it for myself. I decided that this jam was a good opportunity to see what all the fuss with Godot was about, and I don't regret that decision for one second.

![placeholder](/assets/img/blog%20resources/getting-into-godot/1-godot-page.jpg "Godot Homepage")

## Learning Godot

The first order of business was grabbing the engine. From following the main Godot developers on Twitter, I knew that there were two versions of the engine at that point in time: v3.5 which was considered stable, and the latest and greatest v4.0 (beta). Knowing nothing about the differences between the versions, I initially tried using the Godot 4 beta but was immediately met with disappointment as the editor failed to load. Some quick googling revealed that, at the moment, version 4 only supported the [Vulkan](https://www.vulkan.org/) renderer and it turned out that my laptop's graphics card (GeForce 860m) didn't have the required Vulkan drivers. I figured that was a problem for another time and pivoted to using Godot 3.5 instead. Fortunately, the Godot binaries are very small in comparison to other game engines (*cough* Unreal *cough*) so that wasn't a problem at all. It was smooth sailing from that point on with the stable version of Godot. Having spent mountains of time waiting for the interfaces of other game engines to load, I was especially happy to see that the editor loaded in *seconds*!

As this was pretty much my first time using the engine, I turned to the [documentation](https://docs.godotengine.org/en/stable/index.html) to get up-to-speed on what I needed to know to use Godot properly. I was pleasantly surprised to find out that the documentation provided exactly what I was seeking. This [section](https://docs.godotengine.org/en/stable/getting_started/introduction/key_concepts_overview.html) in particular was extremely useful to understand what the fundamental underlying concepts of the engine are.

![placeholder](/assets/img/blog%20resources/getting-into-godot/2-godot-docs.jpg "Godot Docs")

## Playing Around

In order to get a grasp on how the scenes, nodes and signals work in Godot, I pulled the Godot [examples](https://github.com/godotengine/godot-demo-projects) and looked through each of them. It was useful to help with understanding the nodes that are available and how they work. One of the things I try to do whenever I start learning a new engine is to look for guidance on how the project should be structured. This is important when working on larger games or when collaborating with other developers. This [guide](https://docs.godotengine.org/en/stable/tutorials/best_practices/project_organization.html) was useful in that regard. 

Finally, I familiarized myself with Godot's scripting language, GDScript. Godot supports C# as a programming language and I use C# almost daily for my day job, but it feels like Godot was built to be used with GDScript and I didn't want to have to worry about any of the overhead that a garbage-collected language like C# brings. Fortunately, GDScript is very similar to Python, and I've used that a tiny bit already, so getting up-to-speed with GDScript wasn't too bad. In fact, by the end of the learning process, I began to really like GDScript as a companion language to the engine; it's very intuitive for scripting gameplay functionality.

![placeholder](/assets/img/blog%20resources/getting-into-godot/3-gdscript.jpg "GDScript")

## Getting Serious

Once I was fairly satisfied with my Godot learnings, I felt like the best way to solidify my knowledge would be to just jump right into the GitHub Game Off game jam and start building a game in Godot. My teammate and I were able to come up with an idea for the jam's theme (cliché) pretty quickly and we began prototyping the game's systems in Godot right away. For my share of the work, I was tasked with building out the enemy and obstacle spawning routines, as well as the level progression and power-up handlers. I have to say, these tasks went surprisingly smoothly. The built-in functionality in the engine did most of the heavy-lifting and I just had to reference the docs to understand which nodes were appropriate to use for the gameplay processes I was building. After knocking out these tasks in a few days, I began to feel a sense of profound empowerment from the engine; building stuff in Godot was intuitive and fun!

Although the game is not yet finished (we are still a few weeks away from the end of the jam), I still have that same feeling of empowerment as we wrap up development. I'm a firm believer in using the right tool for the job at hand, and for me, Godot has become my goto tool for 2D game development; it's simply a pleasure to use.

We're currently developing the game here: [Shoot Into The Void](https://gameboymarcus.itch.io/shoot-into-the-void). It's constantly being updated as we polish it up for the end of the jam. Please try it out and give us your feedback!

![placeholder](/assets/img/blog%20resources/getting-into-godot/4-shoot-into-the-void.jpg "Shoot Into The Void")