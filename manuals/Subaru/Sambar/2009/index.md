---
layout: default
title: "Subaru Sambar 2009 Manuals"
brand: "Subaru"
model: "Sambar"
year: "2009"
---

# Chassis Codes for {{ page.brand | capitalize }} {{ page.model }} ({{ page.year }})
<ul>
  {% assign chassis_codes = "" | split: "," %}

  {% for p in site.pages %}
    {% assign parts = p.path | split: "/" %}

    {% if parts[0] == "manuals" and parts[1] == page.brand and parts[2] == page.model and parts[3] == page.year and parts.size > 4 %}
      {% assign chassis_code = parts[4] %}

      {% unless chassis_codes contains chassis_code or chassis_code == "index.md" %}
        {% assign chassis_codes = chassis_codes | push: chassis_code %}
      {% endunless %}
    {% endif %}
  {% endfor %}

  {% for chassis_code in chassis_codes %}
    <li><a href="/manuals/{{ page.brand }}/{{ page.model }}/{{ page.year }}/{{ chassis_code }}/">{{ chassis_code }}</a></li>
  {% endfor %}
</ul>