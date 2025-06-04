---
permalink: /projets
layout: page
title: Projets
---

Page en cours de construction.

<ul>
  {% assign category = "projects" %}
  {% for post in site.categories[category] %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
