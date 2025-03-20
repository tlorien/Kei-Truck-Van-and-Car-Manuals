---
layout: default
title: Sitemap
permalink: /sitemap/
---

<h1>Sitemap</h1>
<p>Below is a structured list of all pages on this site.</p>

<ul class="sitemap">
  {% assign sorted_pages = site.pages | sort: "url" %}
  {% assign grouped_pages = {} %}

  <!-- Organize pages into hierarchy -->
  {% for page in sorted_pages %}
    {% assign page_path = page.path | downcase %}
    {% unless page_path contains "404" or page_path contains "sitemap." or page_path contains "robots.txt" or page_path contains "assets/" or page_path contains "feed." or page_path contains ".xml" or page.url == "/" %}
      
      {% assign segments = page.url | split: "/" %}
      {% assign parent_url = "/" %}
      
      <!-- Identify parent pages -->
      {% for segment in segments offset: 1 %}
        {% assign parent_url = parent_url | append: segment | append: "/" %}
        {% if forloop.last %}
          {% assign grouped_pages = grouped_pages | merge: { parent_url => (grouped_pages[parent_url] | default: "") | append: page.url | append: "," } %}
        {% endif %}
      {% endfor %}
    {% endunless %}
  {% endfor %}

  <!-- Display Pages Hierarchically -->
  {% assign displayed = "" %}
  {% for page in sorted_pages %}
    {% assign page_path = page.path | downcase %}
    {% unless displayed contains page.url or page_path contains "404" or page_path contains "sitemap." or page_path contains "robots.txt" or page_path contains "assets/" or page_path contains "feed." or page_path contains ".xml" or page.url == "/" %}
      
      {% assign displayed = displayed | append: page.url | append: "," %}
      <li>
        <a href="{{ page.url | relative_url }}">{{ page.title | default: page.url }}</a>
        {% assign subpages = grouped_pages[page.url] | split: "," %}
        {% if subpages.size > 0 and subpages[0] != "" %}
          <ul>
            {% for subpage_url in subpages %}
              {% assign subpage = site.pages | where: "url", subpage_url | first %}
              {% if subpage %}
                <li><a href="{{ subpage.url | relative_url }}">{{ subpage.title | default: subpage.url }}</a></li>
              {% endif %}
            {% endfor %}
          </ul>
        {% endif %}
      </li>
    {% endunless %}
  {% endfor %}
</ul>
