---
layout: default
---
<div class="sg-body sg-container container">

  {% include index-list.html %}


  {% for p in site.patterns %}

    {% assign name_from_path = p.relative_path | remove: '.html' | split:'/' %}
    {% assign name_parts = name_from_path[3] | replace_first:'-','*' | split:'*' %}
    {% assign name = name_parts[1] %}

    <div class="pattern">
      <a id="{{ name }}"><h2 class="pattern-title">{{ name }}</h2></a>
      {{p.content}}
    </div>
  {% endfor %}

</div>
