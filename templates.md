---
title: Templates
layout: page
---

<div class="sg-body sg-container container">

  {% for p in site.patterns %}

    {% assign name_from_path = p.relative_path | remove: '.html' | split:'/' %}
    {% assign name_parts = name_from_path[3] | replace_first:'-','*' | split:'*' %}
    {% assign name = name_parts[1] %}

    {% if p.relative_path contains 'templates' %}
    <div class="pattern">
      <a id="{{ name }}"><h2 class="pattern-title">{{ name }}</h2></a>
      {{p.content}}
    </div>
    {% endif %}
  {% endfor %}

</div>
