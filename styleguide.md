---
layout: default
block_categories:
  - headings
  - links
---
<div class="sg-body sg-container container">

<ul>
{% for cat in page.block_categories %}
  <li>
    <a href="#{{cat}}">{{cat | capitalize}}</a>
  </li>
{% endfor %}
</ul>


{{ "hello" | slice: -3, 2  }}


{{ site.patterns.size }}



  {% for p in site.patterns %}

    {% assign name_from_path = p.relative_path | remove: '.html' | split:'/' %}
    {% assign name_parts = name_from_path[3] | split:'-' %}
    {% assign name = name_parts[1] %}

    <div class="pattern">
      <h2 class="pattern-title">{{ name }}</h2>
      {{p.content}}
    </div>
  {% endfor %}

</div>
