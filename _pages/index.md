---
permalink: /
layout: page
title: Groupement Français de Recherche pour la mesure sur Fibre Optique en Géosciences
---

> DAS, Sismologie, Géosciences

## À propos

Le G-FROG vise à structurer et rendre visible la communauté des chercheurs et praticiens utilisant les fibres optiques pour des applications en géosciences (Terre solide, surfaces et interfaces, océan-atmosphère, etc.).

Notre réseau favorise l’innovation, la diffusion des connaissances et la promotion des technologies fibre optique (DAS, DTS, etc.) dans la recherche et l’observation.
Partenaires

- EPOS-France
- FormaTerre
- Observatoire de la Côte d'Azur

<div class="post-list">
  <ul class="post-items">
    {% for post in site.posts %}
      <li class="post-item">
        <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
        <p class="post-meta">{{ post.date | date: "%B %d, %Y" }}</p>
        {% if post.excerpt %}
          <p class="post-excerpt">{{ post.excerpt }}</p>
        {% endif %}
      </li>
    {% endfor %}
  </ul>
</div>
