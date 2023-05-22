---
layout: page
title: Nucleo académico
permalink: /projects/
description: Profesores adscritos al Programa de Maestría en Ciencias de la Ingeniería 
nav: true
nav_order: 2
display_categories: [energías renovables, mecatrónica, gestión e innovación administrativa]
horizontal: false
---

La planta docente que conforma este programa dispone de personal altamente capacitado para llevar a cabo la consolidación del programa de maestría. Compuesta por 8 profesores de tiempo completo, de los cuales 4 pertenecen al Sistema Nacional de Investigadores del CONAHCYT, a continuación, se presenta un resumen de las actividades de investigación de los ocho profesores adscritos al Tecnológico de Estudios Superiores de Huixquilucan en donde se propone la creación del programa de MCI.

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
