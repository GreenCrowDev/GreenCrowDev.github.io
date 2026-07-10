---
layout: project
title: "Voronoi Split Screen"
date: 2025-07-15
tags: [godot, gdscript, shader, camera]
description: Dynamic split screen for local multiplayer games.
image: /assets/tools/voronoi-split-screen/img/voronoi_split_screen_005.png
---

**Voronoi Split Screen** is an addon developed internally for my work-in-progress game, Arcade Moto Racing.

![Screenshot](/assets/tools/voronoi-split-screen/img/voronoi_split_screen_001.png)
![Screenshot](/assets/tools/voronoi-split-screen/img/voronoi_split_screen_002.png)

Arcade Moto Racing is a local multiplayer project that mixes party and racing mechanics.
Players can interact with the environment together or split up and explore the surrounding space independently.

While dynamic split screen for two players is generally considered a solved problem, extending it to support an arbitrary number of concurrent players is still largely unexplored and uncommon in commercial games.

![Screenshot](/assets/tools/voronoi-split-screen/img/voronoi_split_screen_003.png)
![Screenshot](/assets/tools/voronoi-split-screen/img/voronoi_split_screen_004.png)

The main inspiration for this project was the GDC talk by Squirrel Eiserloh, [Math for Game Programmers: Juicing Your Cameras With Math](https://youtu.be/tu-Qe66AvtY?si=xcsby2-djQwwLwgI&t=1620).

The talk provides a great starting point and valuable insights into implementing Voronoi-based split-screen cameras for more than two players.

Unfortunately, even their implementation has some unresolved limitations, leaving plenty of room for improvement.

One of the most notable challenges is finding a better way to center players within their Voronoi regions.
To address this, I investigated using [straight skeleton](https://en.wikipedia.org/wiki/Straight_skeleton) algorithms to compute a more balanced center, resulting in a clearer and more stable camera framing.

This required researching and implementing the algorithm in GDScript.

![Screenshot](/assets/tools/voronoi-split-screen/img/voronoi_split_screen_005.png)
![Screenshot](/assets/tools/voronoi-split-screen/img/voronoi_split_screen_006.png)

The tool is currently closed source and used only internally.
After further polishing and optimization, I may consider publishing it.
