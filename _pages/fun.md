---
layout: page
title: fun
permalink: /fun/
description: Life outside the office — family, baseball, movies, games, and the occasional adventure.
nav: true
nav_order: 6
images:
  lightbox2: true
---

<!--
HOW TO ADD PHOTOS
Drop image files into assets/img/fun/ and add one block per photo below.
Each block is a thumbnail that opens full-size in a lightbox when clicked.
Keep the file names simple (no spaces), e.g. baseball-2024.jpg
-->

<div class="row">
{% assign fun_images = site.static_files | where_exp: "f", "f.path contains '/assets/img/fun/'" | sort: "path" %}
{% if fun_images.size == 0 %}
  <div class="col-12">
    <p class="text-muted">Photos are on their way. Check back soon!</p>
  </div>
{% endif %}
{% for f in fun_images %}
  <div class="col-sm-6 col-md-4 mt-3">
    <a href="{{ f.path | relative_url }}" data-lightbox="fun" data-title="{{ f.basename | replace: '-', ' ' | replace: '_', ' ' | capitalize }}">
      <img src="{{ f.path | relative_url }}" class="img-fluid rounded z-depth-1" alt="{{ f.basename | replace: '-', ' ' }}" loading="lazy" />
    </a>
  </div>
{% endfor %}
</div>
