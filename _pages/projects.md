---
layout: page
title: projects
permalink: /projects/
description: 
nav: true
nav_order: 2
display_categories: false
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>

<!--
---
layout: page
title: Supersymmetric black holes
description: This project focuses on studying supersymmetric (SUSY) black holes at long times. The [short paper](https://arxiv.org/abs/2207.00407) gives a summary of the analysis. The [more technical paper](https://arxiv.org/abs/2207.00407) gives a detailed account of the project.
---
-->

<!--
---
layout: page
title: Unruh effect analogue in coupled harmonic oscillator systems
description: The goal of this project is to demonstrate that the difficulty of detecting Unruh radiation in Minkowski spacetime can be overcome by using a mathematically analogous system to model it. In this way, we are able to measure the effect in a different setting while still accounting for the system’s most basic features. We show that the necessary system can be found by considering a pair of coupled optical cavities. We outline how detection of radiation is to be performed in both systems, and how the two processes are related to each other.
redirect: /assets/pdf/Rozenberg_Liza_Fall_JP.pdf
---
-->
