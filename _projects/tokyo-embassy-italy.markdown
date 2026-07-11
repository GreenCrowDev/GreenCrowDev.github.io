---
layout: project
title: "Tokyo Embassy of Italy AR Museum"
date: 2023-01-01
tags: [unity, c#, blender, vuforia, ar]
description: Augmented reality application for archaeological site reconstruction.
image: /assets/projects/tokyo-embassy-italy/img/app_screen_001.jpg
---

During my Architecture studies at the University of Naples Federico II, I was involved in a multidisciplinary research project developed in collaboration with the Embassy of Italy in Tokyo.

The Italian Embassy is located within a historic Edo-period garden in the Mita district of Tokyo.
The site originally belonged to the Matsudaira clan and served as one of their residences during the Tokugawa period.
Remarkably, the garden survived both the Great Kanto Earthquake and the bombings of World War II, preserving much of its original landscape and archaeological heritage.
In recent years, the Embassy has promoted scientific research to study, preserve, and enhance the historical and cultural value of the site.

![Screenshot](/assets/projects/tokyo-embassy-italy/img/embassy_ortophoto.jpg)

Beyond its natural beauty, the garden contains numerous archaeological remains that had yet to be fully studied and documented.

As part of a broader initiative to enhance the site's cultural heritage and make it more accessible to visitors, the research team explored new ways of presenting the archaeological remains while respecting the historical integrity of the garden.
Since interventions on archaeological sites should be as non-invasive as possible, minimizing the physical impact on the environment became one of the project's guiding principles.

The initial phase of the research focused on an ancient Japanese tea house located near the Embassy residence, of which only the original foundation stones remain today.

![Screenshot](/assets/projects/tokyo-embassy-italy/img/current_state_001.jpg)
![Screenshot](/assets/projects/tokyo-embassy-italy/img/current_state_002.jpg)
![Screenshot](/assets/projects/tokyo-embassy-italy/img/current_state_003.jpg)

The archaeological investigation and historical reconstruction were carried out by a multidisciplinary team of archaeologists and architects, who combined historical sources, excavation data, and architectural analysis to recreate the appearance of the building before its disappearance.

![Screenshot](/assets/projects/tokyo-embassy-italy/img/tea_house.png)

To allow visitors to experience the structure as it once stood, the team chose an augmented reality approach to the musealization of the site.
The reconstructed building was modeled in three dimensions based on the archaeological evidence and historical research, then displayed in real time through a mobile AR application used during guided tours.

The objective was to allow visitors to visualize the original building directly on top of its remaining foundations.

Using a mobile application, the camera recognizes the foundation stones and overlays a real-time three-dimensional reconstruction of the historical structure, accurately aligned with the archaeological remains.

Although the application remained a research prototype, the complete experience was fully functional and successfully validated through on-site testing.

![Screenshot](/assets/projects/tokyo-embassy-italy/img/app_screen_001.jpg)
![Screenshot](/assets/projects/tokyo-embassy-italy/img/app_screen_002.jpg)
![Screenshot](/assets/projects/tokyo-embassy-italy/img/app_screen_003.jpg)

I was responsible for the entire software development pipeline, from site acquisition to the final augmented reality experience.

The workflow included:

- Capturing LiDAR scans of the site and its surroundings using an iPad Pro.
- Processing the point clouds to create an accurate digital reference of the environment.
- Modeling the reconstructed tea house in Blender in collaboration with the archaeological and architectural research teams.
- Developing the augmented reality application in Unity.
- Configuring Vuforia Engine to recognize the foundation stones as a three-dimensional target and accurately align the virtual reconstruction with the archaeological site.

![Screenshot](/assets/projects/tokyo-embassy-italy/img/render_001.png)

At the time of development, Vuforia was one of the few augmented reality frameworks capable of reliable three-dimensional object recognition, rather than relying exclusively on printed image markers.
This made it particularly well suited for the project, as it allowed the experience to remain completely non-invasive without introducing additional physical elements into the historical site.

The project combines computer vision, LiDAR scanning, 3D content creation, real-time rendering, and cultural heritage visualization into a single workflow, demonstrating how interactive technologies can support archaeological research, historical reconstruction, and museum experiences while preserving sensitive heritage sites.
