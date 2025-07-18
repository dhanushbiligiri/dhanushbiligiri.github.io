---
layout: page
permalink: /teaching/
title: Teaching
description: Teaching experience, responsibilities, and course materials.
nav: true
nav_order: 6
display_categories: [Fall 2024, Spring 2025]
horizontal: false
---

<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  {% for category in page.display_categories %}
    <a id="{{ category | slugify }}" href=".#{{ category | slugify }}">
      <h2 class="category">{{ category }}</h2>
    </a>
    {% assign categorized_teaching = site.teaching | where: "category", category %}
    {% assign sorted_teaching = categorized_teaching | sort: "importance" %}
    
    {% if page.horizontal %}
    <div class="container">
      <div class="row row-cols-1 row-cols-md-2">
      {% for t in sorted_teaching %}
        {% include projects_horizontal.liquid project=t %}
      {% endfor %}
      </div>
    </div>
    {% else %}
    <div class="row row-cols-1 row-cols-md-3">
      {% for t in sorted_teaching %}
        {% include projects.liquid project=t %}
      {% endfor %}
    </div>
    {% endif %}
  {% endfor %}
{% endif %}
</div>
