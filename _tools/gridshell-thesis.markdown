---
layout: project
title: "Active Bending Timber Gridshell Simulation Addon"
date: 2024-10-22
tags: [c++, rhino, grasshopper, simulation]
description: Addon for the Rhino & Grasshopper suite to simulate post-formed timber gridshells.
image: /assets/tools/gridshell-thesis/img/gridshell_thesis_001.png
---

This project was developed as part of my Architecture graduation thesis at the Università di Napoli Federico II. It is a simulation tool for actively bent timber gridshell structures.

![Screenshot](/assets/tools/gridshell-thesis/img/gridshell_thesis_001.png)

Post-formed timber gridshells are structural systems based on the principle of active bending. They consist of a flat orthogonal grid of linear timber elements that is transformed into a shell through controlled deformations.

By applying external forces, the timber members bend into their final shape, creating lightweight structures that are both aesthetically expressive and structurally efficient.

![Screenshot](/assets/tools/gridshell-thesis/img/gridshell_thesis_002.png)
![Screenshot](/assets/tools/gridshell-thesis/img/gridshell_thesis_003.png)
![Screenshot](/assets/tools/gridshell-thesis/img/gridshell_thesis_004.png)

The goal of the tool is to simulate the form-finding process of these structures, which is traditionally achievable only through physical prototypes or computationally expensive numerical simulations.

![Screenshot](/assets/tools/gridshell-thesis/img/form_finding.png)
![Screenshot](/assets/tools/gridshell-thesis/img/rhino_grasshopper.png)
![Screenshot](/assets/tools/gridshell-thesis/img/visual_scripting.png)

The project implements the **Dynamic Relaxation** algorithm as a library of components for **Grasshopper**, the visual scripting environment of **Rhino**, making advanced structural simulation accessible through a visual workflow.

Its development required extensive research into academic literature, mathematics, physics, and structural engineering.

The library was developed in **C#** using Visual Studio for the Rhino & Grasshopper ecosystem.

It exposes a collection of Grasshopper **components**, allowing architects and engineers with little or no programming experience to design and simulate their own timber gridshells while abstracting away the underlying physics and numerical methods.
