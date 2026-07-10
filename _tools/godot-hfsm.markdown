---
layout: project
title: "Godot Hierarchical FSM"
date: 2026-01-01
tags: [godot, c++, fsm]
description: A lightweight hierarchical finite state machine for Godot.
image: /assets/tools/godot-hfsm/img/godot_hfsm_001.png
---

**Godot Hierarchical FSM** is an addon that provides a simple, lightweight implementation of hierarchical finite state machines for the Godot Engine.

While most existing implementations rely on node-based state machines, I chose a code-first approach.
This keeps the state logic centralized, makes code reviews and diffs easier to follow, and avoids unnecessary scene complexity.

At the same time, state logic can still be split into reusable components when needed, allowing flexible architectures without enforcing a specific design pattern.

The API is designed to be simple and self-documenting.

Here's an example of a minimal state machine:

```gdscript
enum State {
	INIT,
	MENU,
	MENU_LOGO,
	MENU_MAIN,
	GAMEPLAY,
	EXIT,
}

var fsm: HFSM

func _setup_fsm() -> void:
	fsm = HFSM.init_fsm(State)

	# Global flow.
	fsm.add_transition(State.INIT, State.MENU, &"to_menu")
	fsm.add_transition(State.MENU, State.GAMEPLAY, &"start_game")
	fsm.add_transition(State.GAMEPLAY, State.MENU, &"back_to_menu")
	fsm.add_transition(State.MENU, State.EXIT, &"exit")

	# Menu flow.
	fsm.add_transition(State.MENU_LOGO, State.MENU_MAIN, &"continue")

	# Debug: print state changes.
	for state in fsm.states.values():
		state.entered.connect(func(): print("Entered: ", state.name))
		state.exited.connect(func(): print("Exited: ", state.name))

	fsm.start()

func _ready() -> void:
	_setup_fsm()

func _process(delta: float) -> void:
	fsm.process(delta)
```

The library leverages existing GDScript features to keep the API compact and familiar.
States are defined using a regular enum, providing a single, centralized place to describe an entity's behavior.

Hierarchies are inferred directly from enum names using a simple naming convention, without requiring any additional configuration:

```gdscript
MENU,
MENU_LOGO, # Child of MENU
MENU_MAIN, # Child of MENU
```

Besides character, enemy, and NPC behaviors, the library was also designed to handle complex UI flows.
Hierarchical states make it easy to manage screen navigation, menus, and history while keeping the implementation entirely script-driven.

The tool is currently closed source and used internally.
Public release is being considered after further polishing and optimization.
