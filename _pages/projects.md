---
layout: collection
title: Projects
permalink: /projects/
collection: projects
---

<div id="map" style="height: 600px; width: 100%;"></div>

<link 
  rel="stylesheet" 
  href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"
/>

<script 
  src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js">
</script>

<style>
img.huechange { filter: hue-rotate(120deg); }
</style>

<script>
  const map = L.map('map').setView([20, 0], 2);

  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    maxZoom: 19,
    attribution: '© OpenStreetMap'
  }).addTo(map);

  const markers = [
  {% for project in site.projects %}
    { name: {{ project.title }}, coords: [{{ project.latitude }}, {{ project.longitude }}], url: {{ project.url}} },
  {% endfor %}
  ];

  markers.forEach(m => {
    const marker = L.marker(m.coords).addTo(map);
    marker.bindPopup(`<b>${m.name}</b><br><a href="${m.url}">Voir la page</a>`);
    marker._icon.classList.add("huechange");
  });
</script>
