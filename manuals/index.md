---
layout: default
title: All Manuals
---

# Car Brands
<ul>
  {% assign brands = "" | split: "," %}  {# Initialize an empty array #}

  {% for page in site.pages %}
    {% if page.path contains "manuals/" %}
      {% assign brand_name = page.path | split: "/" | slice: 1, 1 | first %}

      {% unless brands contains brand_name %}
        {% assign brands = brands | push: brand_name %}
      {% endunless %}
    {% endif %}
  {% endfor %}

  {% for brand in brands %}
    <li><a href="/manuals/{{ brand }}/">{{ brand | capitalize }}</a></li>
  {% endfor %}
</ul>
