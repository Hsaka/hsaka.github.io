---
date: 2017-06-16 02:03:59
layout: post
title: "Quicket Update"
subtitle: A Cricket Game For People Who Don't Like Cricket
description: Applying a coat of polish on the gentleman's game
image: /assets/img/covers/quicket-update-big.jpg
optimized_image: /assets/img/covers/quicket-update-opt.jpg
category: gamedev
tags:
  - caribgames
  - phaser
author: hsaka
paginate: false
---

**Update - Quicket is a staff pick on an issue of the [Phaser World newsletter](https://madmimi.com/p/7bb06a?utm_content=bufferc774c&utm_medium=social&utm_source=twitter.com&utm_campaign=buffer)!**

In a [previous post](https://hsaka.github.io/quicket/), we built a cricket game as part of our series on Caribbean Games. We liked the game so much that we decided to expand it further this week. It's quite a rare occurrence that a game that we built is unique, fun and well-received, so it made sense to polish it up from the initial post. Quicket was literally built in one day and even though its core gameplay loop was engaging, we knew a lot more could be done with it.

## Leaderboards

If you played the original Quicket from last week's post, you would have noticed that there wasn't really any reason to keep playing other than to try to beat your own score. One of the first improvements we made was to add a highscores list to the game so that you can compete against other Quicket players for the most runs scored. In our experience, the existence of a leaderboard in games tends to encourage players to attempt to get to the number 1 spot. After adding highscores, we noticed a fierce competition had begun among the tiny player base of the game.

![placeholder](/assets/img/blog%20resources/quicket/4-quicket.jpg "Quicket")

The screenshot above shows the latest (as of 16/06/2017 11:00am) highscores for Quicket. It's interesting to note that when the leaderboard was implemented last week, the highest scores were in the high 100s. They are now at 300+ and climbing higher every day.

## Offline Saves

With the ability to submit your highscores comes the necessity for supporting offline saves. Several people requested that we add this feature because they wanted to play while travelling or waiting at the bank where they might not have access to the internet. Without internet access, you would not be able to send your scores to the server. We therefore had to cache the scores locally until internet access was available in order to ensure that your scores will always be submitted at some point regardless of where you are.

## Run Chase Mode

The original game only had one mode: Classic, which is great for jumping in for a quick try at the leaderboard and then jumping out. We wanted to include a mode that had a level progression system that would give some sense of accomplishing a task. The Run Chase mode has a potentially infinite number of levels, with each one having a run target that you have to reach under a different set of conditions for the number of balls and wickets remaining. Each level's conditions are randomly generated within a restricted range of values to ensure that the level is fair but challenging.

![placeholder](/assets/img/blog%20resources/quicket/5-quicket.jpg "Quicket")

## Challenges

Finally, we added several challenge modes to the game, each with its own individual leaderboards. The challenge modes ask you to get the most number of runs that you can under several different constraints. These modes are shown below.

![placeholder](/assets/img/blog%20resources/quicket/6-quicket.jpg "Quicket")

## Android App on Google Play

All of these new features were added to the game with the intention of submitting it as an app on the app stores. One of the great things about developing games in HTML5 is that they can work on many different platforms using the same codebase. We used Cocoon.io to wrap the game into a native android app and submitted it to the Google Play Store. We intend to build an iOS version of Quicket and submit it soon.

Download the game for Android phones [here](https://play.google.com/store/apps/details?id=com.gamepyong.quicket&pcampaignid=MKT-Other-global-all-co-prtnr-py-PartBadge-Mar2515-1).