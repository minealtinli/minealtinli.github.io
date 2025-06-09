---
layout: page
title: research interests
permalink: /projects/
description:
nav: true
nav_order: 2
display_categories: [work]
horizontal: false
---
Mosquitoes are central vectors for numerous emerging and re-emerging viral diseases, yet their biology is shaped by far more than the pathogens they transmit. As hosts to a wide array of arboviruses (viruses that alternate between mosquito and vertebrate hosts), insect-specific viruses (ISVs) (restricted to insect hosts), and diverse symbiotic microbiota, mosquitoes represent complex systems where microbial interactions influence both viral persistence and transmission dynamics. These interactions (virus–virus, microbe–virus, and host–microbe) are further modulated by the mosquito’s innate immune system, especially RNA interference (RNAi), a central antiviral pathway in insects.

My research investigates these interactions comparatively across different biological scales, from cellular mechanisms of immune modulation to population level dynamics, to uncover the underlying processes that determine whether and how viruses are transmitted. These interactions shape mosquito immunity, tissue tropism and infection outcomes, and may be repurposed or engineered for novel vector control strategies. Understanding these relationships provides a foundation for translational approaches that aim to disrupt pathogen transmission at its ecological and molecular roots.


<!-- pages/projects.md -->
<div class="projects">
<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
