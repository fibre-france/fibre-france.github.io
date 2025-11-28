---
permalink: /projects/
title: Projects
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
    { name: "{{ project.title }}", coords: [{{ project.latitude }}, {{ project.longitude }}], url: "{{ project.url }}" },
  {% endfor %}
  ];

  markers.forEach(m => {
    const marker = L.marker(m.coords).addTo(map);
    marker.bindPopup(`<b>${m.name}</b><br><a href="${m.url}">Voir la page</a>`);
    marker._icon.classList.add("huechange");
  });
</script>

<style>
.project-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(320px, 1fr)); gap: 1rem; margin-top: 1rem; }
.project-card { background: #fff; border-radius: 8px; padding: 1rem; box-shadow: 0 2px 8px rgba(0,0,0,0.08); }
.project-card h2 { margin: 0 0 0.5rem; font-size: 1.1rem; }
.project-meta { font-size: 0.95rem; color: #333; line-height: 1.4; }
.project-meta .label { font-weight: 600; margin-right: 0.25rem; }
.project-card a.button { display: inline-block; margin-top: 0.5rem; padding: 0.35rem 0.6rem; background: #2b7cff; color: #fff; border-radius: 4px; text-decoration: none; }
</style>

<div class="project-grid">
{% for project in site.projects %}
  <div class="project-card">
    <h2>{{ project.title }}</h2>
    <div class="project-meta">
      <div><span class="label">Principal Investigator:</span>{{ project.pi }}</div>
      <div><span class="label">Institution:</span>{{ project.institution }}</div>
      <div><span class="label">Contact:</span> <a href="mailto:{{ project.contact }}">{{ project.contact }}</a></div>
      <div><span class="label">Duration:</span> {{ project.start_date }} - {{ project.end_date }}</div>
      <div><span class="label">Categories:</span> {{ project.categories | join: ", " }}</div>
      <div><span class="label">Location:</span> {{ project.latitude }}°, {{ project.longitude }}°</div>
    </div>
    <p><a class="button" href="{{ project.url }}">Voir la page</a></p>
  </div>
{% end for %}
</div>