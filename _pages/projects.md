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

<script>
  const map = L.map('map').setView([20, 0], 2);

  L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
    maxZoom: 19,
    attribution: '© OpenStreetMap'
  }).addTo(map);

  const markers = [
    { name: "ABYSS", coords: [-72.2, -31.1], url: "/projects/abyss" },
  ];

  markers.forEach(m => {
    L.marker(m.coords)
      .addTo(map)
      .bindPopup(`<b>${m.name}</b><br><a href="${m.url}">Voir la page</a>`);
  });
</script>
