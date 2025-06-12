---
permalink: /instruments/
title: "Instruments"
---

Explore our curated collection of scientific instruments available for borrowing. Whether you're conducting research, teaching, or pursuing a personal project, these tools are here to support your scientific endeavors. Browse the list below to find detailed information, images, and descriptions for each instrument.

{% for instrument in site.instruments %}
<div style="display: flex; align-items: flex-start; margin-bottom: 2em;">
    <a href="{{ instrument.url }}">
        <img src="{{ instrument.thumbnail }}" alt="Thumbnail for {{ instrument.company }} {{ instrument.instrument }}" style="width: 150px; min-width: 150px; max-width: 150px; height: auto; margin-right: 1.5em; border-radius: 4px; object-fit: cover;" />
    </a>
    <div>
        <a href="{{ instrument.url }}" style="text-decoration: none; color: inherit;">
            <span style="display: block; font-size: 1.1em; font-weight: bold; color: #2a4d69; margin-bottom: 0.2em;">{{ instrument.company }}</span>
            <span style="display: block; font-size: 1.4em; font-weight: 600; color: #1b2838; margin-bottom: 0.5em;">{{ instrument.instrument }}</span>
        </a>
        <p style="margin-top: 0;">{{ instrument.excerpt }}</p>
    </div>
</div>
{% endfor %}
