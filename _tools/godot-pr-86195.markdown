---
layout: project
title: "Godot PR: Add closed property to Curve3D"
date: 2023-12-15
tags: [godot, c++, open source]
description: Godot Engine Curve3D class improvement.
image: /assets/tools/godot-pr-86195/img/godot_pr_86195_002.png
---

**Godot Engine PR #86195** adds a `closed` property to the `Curve3D` class.

Previously, 3D curves in Godot didn't support a native closed mode.
As a workaround, developers had to manually duplicate the first point at the end of the curve.

This approach had several drawbacks:

* Redundant control points, poorer UX, and manual adjustments every time the curve changed.
* Tilt data didn't interpolate correctly across the closing segment.
* Explicitly marking a curve as closed is useful for many workflows, especially mesh extrusion and procedural generation, where distinguishing between open and closed curves is important.

![Screenshot](/assets/tools/godot-pr-86195/img/godot_pr_86195_001.png)

The implementation involved:

* Changing the color of the start and end points (especially useful for closed curves, where the beginning of the curve is otherwise unclear).
* Displaying the **In** handle for the start point and the **Out** handle for the end point when `closed = true`.
* Showing the **In** and **Out** properties in the Inspector when `closed = true`.
* Replacing the **Close Curve** button in `Path3DEditorPlugin` with a toggle that switches the `closed` property on and off.
* Adding the corresponding documentation.

![Screenshot](/assets/tools/godot-pr-86195/img/godot_pr_86195_002.png)

You can read the full discussion and implementation details in the pull request: [Add closed property to Curve3D](https://github.com/godotengine/godot/pull/86195).
