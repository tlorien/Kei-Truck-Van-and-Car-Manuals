---
layout: default
title: "Subaru Sambar Manuals"
permalink: "/manuals/Subaru/Sambar/"
brand: "Subaru"
model: "Sambar"
---

# Years for {{ page.brand | capitalize }} {{ page.model }}
<ul>
  {% assign years = "" | split: "," %}

  {% for p in site.pages %}
    {% assign parts = p.path | split: "/" %}

    {% if parts[0] == "manuals" and parts[1] == page.brand and parts[2] == page.model and parts.size > 3 %}
      {% assign year_name = parts[3] %}

      {% unless years contains year_name or year_name == "index.md" %}
        {% assign years = years | push: year_name %}
      {% endunless %}
    {% endif %}
  {% endfor %}

  {% for year in years %}
    <li><a href="/manuals/{{ page.brand }}/{{ page.model }}/{{ year }}/">{{ year }}</a></li>
  {% endfor %}
</ul>