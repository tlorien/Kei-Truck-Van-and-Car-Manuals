---
layout: default
title: "Subaru Sambar 2009 GBD-TT2 Manual"
permalink: "/manuals/Subaru/Sambar/2009/GBD-TT2"
brand: "Subaru"
model: "Sambar"
year: "2009"
chassis: "GBD-TT2"
---

# Sections for {{ page.brand | capitalize }} {{ page.model }} ({{ page.year }}) [{{ page.chassis }}]
<ul>
  {% assign sections = "" | split: "," %}

  {% for p in site.pages %}
    {% assign parts = p.path | split: "/" %}

    {% if parts[0] == "manuals" and parts[1] == page.brand and parts[2] == page.model and parts[3] == page.year and parts[4] == page.chassis and parts.size > 5 %}
      {% assign section_name = parts[5] | replace: ".md", "" %}

      {% unless sections contains section_name or section_name == "index" %}
        {% assign sections = sections | push: section_name %}
      {% endunless %}
    {% endif %}
  {% endfor %}

  {% for section in sections %}
    <li><a href="/manuals/{{ page.brand }}/{{ page.model }}/{{ page.year }}/{{ page.chassis }}/{{ section }}/">
      {{ section | replace: "-", " " | capitalize }}
    </a></li>
  {% endfor %}
</ul>