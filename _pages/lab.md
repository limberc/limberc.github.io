---
layout: default
title: "Our Lab"
permalink: /lab/
---

<div class="lab-grid">
  {% for member in site.data.lab_members %}
    <div class="lab-card">
      <img src="{{ member.image }}" alt="{{ member.name }}" />
      <h3>{{ member.name }}</h3>
      <strong>{{ member.role }}</strong>
      <p>{{ member.intro }}</p>
    </div>
  {% endfor %}
</div>
