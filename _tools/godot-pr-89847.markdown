---
layout: project
title: "Godot PR: UX and stability improvements for Path3D node"
date: 2024-03-24
tags: [godot, c++, open source]
description: Godot Engine Path3D editor usability improvement.
image: /assets/tools/godot-pr-89847/img/godot_pr_89847_001.png
---

**Godot Engine PR #89847** improves the editing experience of `Path3D` and `Curve3D` in the editor.

Many developers had reported usability issues and bugs when editing 3D curves.

One of the most prominent issues was the inability to select control points when multiple handles overlapped.
This was generally caused by a cluttered UI with too many handles visible at the same time.

![Screenshot](/assets/tools/godot-pr-89847/img/godot_pr_89847_001.png)

The work involved splitting the editor into multiple interaction modes and designing a new toolbar icon:

* Show the transform gizmo only in **Select Points** mode.
* Show secondary handles only in **Select Control Points** mode.
* Clear the subgizmo selection when changing modes.
* Add a **Select Tilt Points** mode that displays only the tilt handles.

![Screenshot](/assets/tools/godot-pr-89847/img/godot_pr_89847_002.png)

You can read the full discussion and implementation details in the pull request: [UX and stability improvements for Path3D node](https://github.com/godotengine/godot/pull/89847).
