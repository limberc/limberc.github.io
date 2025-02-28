---
layout: default
title: "Our Lab"
permalink: /lab/
---

<div class="container lab-members">
  <div class="row">
    {% for member in site.data.lab_members %}
    <div class="col-md-4 col-sm-6 lab-member">
      <div class="member-card">
        <img src="{{ member.image }}" alt="{{ member.name }}" class="member-portrait">
        <h3 class="member-name">{{ member.name }}</h3>
        <p class="member-role"><strong>{{ member.role }}</strong></p>
        <p class="member-intro">{{ member.intro }}</p>
      </div>
    </div>
    {% endfor %}
  </div>
</div>
