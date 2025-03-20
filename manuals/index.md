---
layout: default
title: All Manuals
permalink: /manuals/
---

# Car Brands
<ul>
  {% assign brands = "" | split: "," %}

  {% for page in site.pages %}
    {% if page.path contains "manuals/" and page.path != "manuals/index.md" %}
      {% assign parts = page.path | split: "/" %}
      {% assign brand_name = parts[1] %}

      {% unless brands contains brand_name or brand_name == "index.md" %}
        {% assign brands = brands | push: brand_name %}
      {% endunless %}
    {% endif %}
  {% endfor %}

  {% for brand in brands %}
    <li><a href="/manuals/{{ brand }}/">{{ brand | capitalize }}</a></li>
  {% endfor %}
</ul>
