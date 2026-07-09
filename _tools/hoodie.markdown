---
layout: project
title: "Hoodie"
date: 2026-07-08
tags: [godot, c++, procedural]
description: A procedural mesh generation library.
image: /assets/tools/hoodie/img/hoodie_001.png
---

**Hoodie** is a procedural mesh generation library for Godot Engine.

![Screenshot](/assets/tools/hoodie/img/hoodie_001.png)

Coming from an architecture background, I used Rhino and Grasshopper extensively for procedural design of furniture and structures.

This tool takes inspiration from that workflow, as well as from other procedural content creation tools used in game development, such as SideFX Houdini and Blender Geometry Nodes.

While working on my projects, I often found opportunities to apply procedural geometry generation to things like paths, environments, and other systems based on mathematical rules and mesh manipulation.

I wanted a way to build these systems visually, so I decided to create my own library with a visual scripting approach.

Luckily, I found that some of the groundwork had already been done. Bastiaan Olij had built a similar open-source library, which I used as a reference to kick-start this project.

The tech stack is based on Godot's GDExtension system, which allows developers to create add-ons using C++ while having almost direct access to the Godot Engine API.

The library features a wide variety of nodes that allow custom logic and procedural geometry generation based on curvature values, derivatives, and other geometric properties used to shape meshes.

![Screenshot](/assets/tools/hoodie/img/hoodie_002.jpeg)

Hoodie is open source and can be found here:

[GitHub - Hoodie Legacy](https://github.com/GreenCrowDev/hoodie-legacy)

A newer version with a more robust architecture is currently a work in progress:

[GitHub - Hoodie](https://github.com/GreenCrowDev/hoodie)

You can see Hoodie in action in my development logs on my [YouTube channel](https://www.youtube.com/watch?v=F20C7CQzz-Y&list=PL_rPTnOU23F0o3Mf9EDbX-SqA3ET970jT&index=4).
