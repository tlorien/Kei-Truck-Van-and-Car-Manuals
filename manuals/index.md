---
layout: default
title: All Manuals
---

# Car Brands
{% assign brands = site.pages | map: "path" | map: "manuals" | uniq %}
<ul>
  {% for brand in brands %}
    <li><a href="/manuals/{{ brand }}/">{{ brand | capitalize }}</a></li>
  {% endfor %}
</ul>
