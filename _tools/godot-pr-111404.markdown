---
layout: project
title: "Godot PR: Improve multiplayer support by implementing PlayerID"
date: 2025-10-08
tags: [godot, c++, open source]
description: Implement better multiplayer input support.
image: /assets/tools/godot-pr-111404/img/godot_pr_111404_001.png
---

**Godot Engine PR #111404** introduces a `PlayerID` abstraction to improve local multiplayer input support.

The PR is still under active discussion and has not yet been merged, although it is currently in a working state.

This work originates from a proposal by coffeebeats, [Improve local multiplayer support by tracking InputEvents and UI focus per player](https://github.com/godotengine/godot-proposals/issues/10070).

The [original implementation](https://github.com/godotengine/godot/pull/102412) also included multiplayer input support for `Control` nodes, enabling built-in split-screen UI support, which is currently difficult to achieve in Godot.

Following maintainers' feedback, the work was split into multiple pull requests. This PR focuses solely on introducing the `PlayerID` abstraction, which decouples physical input devices from the players using them.

The main goal is to make it easy to distinguish input events from different players in code, without relying on separate Input Map actions for each player and device.

This also allows multiple players to share the same device, such as a keyboard, with only minimal custom logic.

Backwards compatibility is preserved through default function arguments.

```gdscript
# Player 1.
if Input.is_action_just_pressed("ui_accept", false, PLAYER_ID_P1): # Input.is_action_just_pressed("ui_accept", false) is equivalent.
    print("P1 ui_accept just pressed")

# Player 2.
if Input.is_action_just_pressed("ui_accept", false, PLAYER_ID_P2):
    print("P2 ui_accept just pressed")

# Assign device 0 to player 2.
Input.set_joy_player_id(0, PLAYER_ID_P2)
```

The new API allows developers to assign devices as they are connected and implement their own mapping logic between physical devices and players using `PlayerID`.

`PlayerID` is then passed as an optional argument to the existing `Input` singleton methods, such as `is_action_just_pressed()`, to specify which player's input should be evaluated.

* `PlayerID` is a new enum used to assign inputs to players and query which player generated an input event.
* Methods such as `Input::is_action_pressed()` now accept an optional `PlayerID` parameter.
* Joypad events in the `InputMap` now default to `ALL_DEVICES`, since the recommended way to distinguish players is through `PlayerID`. Assigning a specific device ID in the Input Map is still supported for custom workflows, but is no longer intended to be the primary approach.
* Keyboard, mouse, and touch inputs can be assigned to players other than P1 through `keyboard_player_id_override`, `mouse_player_id_override`, and `touch_player_id_override`.
* Newly connected devices are automatically assigned a `PlayerID` in order (device 0 → P1, device 1 → P2, and so on).

You can read the full discussion and implementation details in the pull request: [Input: Improve multiplayer support by implementing PlayerID](https://github.com/godotengine/godot/pull/111404).
