---
layout: default
title: "Subaru Manuals"
permalink: "/manuals/Subaru/"
brand: "Subaru"
---

# Models for {{ page.brand | capitalize }}
<ul>
  {% assign models = "" | split: "," %}

  {% for p in site.pages %}
    {% assign parts = p.path | split: "/" %}

    {% if parts[0] == "manuals" and parts[1] == page.brand and parts.size > 2 %}
      {% assign model_name = parts[2] %}

      {% unless models contains model_name or model_name == "index.md" %}
        {% assign models = models | push: model_name %}
      {% endunless %}
    {% endif %}
  {% endfor %}

  {% for model in models %}
    <li><a href="{{ "/manuals/" | append: page.brand | append: "/" | append: model | append: "/" | relative_url }}">{{ model }}</a></li>
  {% endfor %}
</ul>