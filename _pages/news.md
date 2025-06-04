---
permalink: /news
layout: page
title: Actualité
---

Page en cours de construction.

<ul>
  {% assign category = "news" %}
  {% for post in site.categories[category] %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
