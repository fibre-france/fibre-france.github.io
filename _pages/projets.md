---
permalink: /projets
layout: page
title: Projets
---

Page en cours de construction.

<ul>
  {% assign category = "projets" %}
  {% for post in site.categories[category] %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
