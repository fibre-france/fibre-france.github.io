---
permalink: /about/
title: "About"
---

# Ma carte du monde

Voici une carte intégrée dans du Markdown :

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
    { name: "Paris", coords: [48.8566, 2.3522], url: "/pages/paris.html" },
    { name: "Tokyo", coords: [35.6895, 139.6917], url: "/pages/tokyo.html" },
    { name: "New York", coords: [40.7128, -74.0060], url: "/pages/newyork.html" }
  ];

  markers.forEach(m => {
    L.marker(m.coords)
      .addTo(map)
      .bindPopup(`<b>${m.name}</b><br><a href="${m.url}">Voir la page</a>`);
  });
</script>
