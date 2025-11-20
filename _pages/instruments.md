---
permalink: /instruments/
title: "Instruments"
---

Explore our curated collection of scientific instruments available for borrowing. Whether you're conducting research, teaching, or pursuing a personal project, these tools are here to support your scientific endeavors. Browse the list below to find detailed information, images, and descriptions for each instrument.

Currently, one instrument is available for reservation. This instrument is a Febus A1 DAS from the ANR MONIDAS project. You can book the instrument for your next campaign in this calendar and send an email to Diane Rivet.

For the moment, there is no “ticket modérateur,” and therefore you must cover the full cost of round-trip shipping to OCA between experiments, or shipping to the next experiment site.

[Réservation DAS Mobile](https://docs.google.com/spreadsheets/d/14kikqxjNgn07JRaNIiZMTrdnUB7TYoG37IgzA2vU55w/edit?gid=0#gid=0)

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
