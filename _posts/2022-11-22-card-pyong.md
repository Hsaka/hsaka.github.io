---
date: 2017-05-31 00:16:02
layout: post
title: "Card Pyong"
subtitle: The Mother of all Card Games
description: Allowing for any card game in the world to be played
image: /assets/img/covers/card-pyong-big.jpg
optimized_image: /assets/img/covers/card-pyong-opt.jpg
category: gamedev
tags:
  - postmortem
  - libgdx
author: hsaka
paginate: false
---

Imagine, if you will, that I gave you a deck of cards. Provided that you knew the rules and had people to play with, you could potentially play any card game in the world. Now imagine if you had a deck of cards that existed only in a virtual environment. If you were given the ability to manipulate that virtual deck of cards in the same manner as you would a real deck and you could do this while connected to other players online, you could potentially play any card game from anywhere and with anyone in the world. This is the premise of Card Pyong; an online multiplayer game that simulates a deck of cards.

## The History

Card Pyong was released in 2014. It was built using the [LibGDX](https://libgdx.com/) framework and uses the [KryoNet](https://github.com/EsotericSoftware/kryonet) library for its networking. The original idea for the game was based on a conversation that I had with a friend of mine. We speculated that if we could create a game that gave players the power and flexibility to play any card game that they wanted to play with their friends online, maybe people would take an interest in it. We knew that making such a complex game with such a wide degree of player interactions would not be a trivial task. It wasn't.

## The Build

Card Pyong is an online multiplayer game. As such, there needed to be a way for players to connect and determine what card game they wanted to play. The Lobby accomplishes this by allowing players to chat with each other and view the list of game rooms.

![placeholder](/assets/img/blog%20resources/card-pyong/1-card-pyong.jpg "Card Pyong")

Players can also create their own rooms. Once in a room, players can setup the game they want to play. Rooms can hold a maximum of 4 players at a time. When the room master decides that the game is properly setup, they can start the game.

![placeholder](/assets/img/blog%20resources/card-pyong/2-card-pyong.jpg "Card Pyong")

The main functionality of Card Pyong lies in the card interactions. The game needed to provide a simple and intuitive way for players to manipulate the deck as well as each individual card. If you will recall, there are at most 4 players in the game room at a time. Each of these players may be manipulating cards or other items in the game. It was therefore necessary to provide a log of the actions that all players are taking during the game so that players can ensure that there aren't any shenanigans going on. It was also necessary to impose certain rules such as restricting deck manipulation to one player at a time. Once a player has selected the deck, it is highlighted in that player's colour and they can drag it around or perform actions on it.

![placeholder](/assets/img/blog%20resources/card-pyong/3-card-pyong.jpg "Card Pyong")

Some of the actions that can be performed on the deck are:
* Shuffle Deck - randomly arranges the cards in the deck.
* Cut Deck - cuts the deck randomly
* Deal Cards - puts the deck in deal mode. In this mode, you can deal cards to players by flinging cards out of the deck or by right-clicking anywhere on the table to throw a card at that position.
* Move - puts the deck in movement mode. This is the default mode for the deck and is only shown when the deck is in Deal mode.
* Flip top card - Pulls the first card from the deck and flips it face up.
* Take top card - Pulls the first card from the deck and adds it to your hand.
* Draw top card - Pulls the first card from the deck face down.
* Draw bottom card - Pulls the last card from the deck face down.
* Scatter cards - Randomly flings cards from the deck either face up or face down.

Similarly, Card Pyong allows you to manipulate a single card or a group of cards. Players are able to add cards to their hand which effectively locks the cards to that player, preventing other players from seeing or manipulating the cards. The actions that can be performed on cards can be seen below.

![placeholder](/assets/img/blog%20resources/card-pyong/4-card-pyong.jpg "Card Pyong")

Using these simple actions for deck and card manipulation, practically any card game can be played. The game even allows you to add other items to the table such as poker chips and money. The flow below shows a gameplay walkthrough for playing the card game Romi in Card Pyong:

![placeholder](/assets/img/blog%20resources/card-pyong/5-card-pyong.jpg "Card Pyong")

You can download Card Pyong [here](http://www.gamepyong.com/card_pyong/).