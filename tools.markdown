---
layout: page
title: Tools
permalink: /tools/
---

{% assign all = site.tools | sort: "date" | reverse %}

<link rel="stylesheet" href="/assets/css/section-header.css">
<link rel="stylesheet" href="/assets/css/project-card-horizontal.css">

<style>
  .project-list {
    display: flex;
    flex-direction: column;
    padding: 0 8px 0 8px;
    gap: 8px;
  }
</style>

<div class="projects-page">
  {% include section-header.html title=page.title %}

  <div class="project-list">
    {% for item in all %}
      {% include project-card-horizontal.html project=item %}
    {% endfor %}
  </div>
</div>