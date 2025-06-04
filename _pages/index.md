---
permalink: /
layout: page
list_tile: Actualité
list_category: news
---

Groupement Français de Recherche pour la mesure sur Fibre Optique en Géosciences

> DAS, Sismologie, Géosciences

## À propos

Le G-FROG vise à structurer et rendre visible la communauté des chercheurs et praticiens utilisant les fibres optiques pour des applications en géosciences (Terre solide, surfaces et interfaces, océan-atmosphère, etc.).

Notre réseau favorise l’innovation, la diffusion des connaissances et la promotion des technologies fibre optique (DAS, DTS, etc.) dans la recherche et l’observation.
Partenaires

- EPOS-France
- FormaTerre
- Observatoire de la Côte d'Azur


{%- if posts.size > 0 -%}
  {%- if page.list_title -%}
    <h2 class="post-list-heading">{{ page.list_title }}</h2>
  {%- endif -%}
  <ul class="post-list">
    {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
    {%- assign category = page.list_category -%}
    {%- for post in site.categories[category] -%}
    <li>
      <span class="post-meta">{{ post.date | date: date_format }}</span>
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title | escape }}
        </a>
      </h3>
      {%- if site.minima.show_excerpts -%}
        {{ post.excerpt }}
      {%- endif -%}
    </li>
    {%- endfor -%}
  </ul>

  {% if site.paginate %}
    <div class="pager">
      <ul class="pagination">
      {%- if paginator.previous_page %}
        <li>
          <a href="{{ paginator.previous_page_path | relative_url }}" class="previous-page" title="Go to Page {{ paginator.previous_page }}">
            {{ paginator.previous_page }}
          </a>
        </li>
      {%- else %}
        <li><div class="pager-edge">•</div></li>
      {%- endif %}
        <li><div class="current-page">{{ paginator.page }}</div></li>
      {%- if paginator.next_page %}
        <li>
          <a href="{{ paginator.next_page_path | relative_url }}" class="next-page" title="Go to Page {{ paginator.next_page }}">
            {{ paginator.next_page }}
          </a>
        </li>
      {%- else %}
        <li><div class="pager-edge">•</div></li>
      {%- endif %}
      </ul>
    </div>
  {%- endif %}
{%- endif -%}
