---
layout: manual
title: "Subaru Sambar 2009 GBD-TT2 Manual"
permalink: "/manuals/Subaru/Sambar/2009/GBD-TT2/"
brand: "Subaru"
model: "Sambar"
year: "2009"
chassis: "GBD-TT2"
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Subaru Sambar Manual</title>
    <link rel="stylesheet" href="{{ './assets/styles/sambar.css' }}">
</head>
<body>
    <div class="manual-header">
        <div class="subaru-logo-text">
            <img src="{{ site.baseurl }}/assets/images/brand-logos/subaru.svg" alt="Subaru Logo" class="subaru-logo">
            <span class="subaru-text">SUBARU</span>
        </div>

        <div class="chassis-codes">
            <strong>GBD-TT1 EBD-TT1</strong><br>
            <strong>GBD-TT2 EBD-TT2</strong><br>
            <strong>GBD-TV1 EBD-TV1</strong><br>
            <strong>GBD-TV2 EBD-TV2</strong>
        </div>

        <div class="sambar-block">
            <span class="sambar-name">SAMBAR</span>
        </div>

        <div class="sub-title">
            <span>New car manual</span><br>
            <span>Maintenance manual</span>
        </div>
    </div>
    <br>
</body>
</html>

# {{ page.title }}
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
    <li><a href="{{ "/manuals/" | append: page.brand | append: "/" | append: page.model | append: "/" | append: page.year | append: "/" | append: page.chassis | append: "/" | append: section | append: "/" | relative_url }}">
      {{ section | replace: "-", " " | capitalize }}
    </a></li>
  {% endfor %}
</ul>