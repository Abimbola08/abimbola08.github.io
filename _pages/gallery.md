---
layout: page
title: gallery
permalink: /gallery/
description: A few snapshots from life outside the office — family, travel, baseball, and the occasional adventure.
nav: true
nav_order: 6
images:
  lightbox2: true
---

<!--
HOW TO ADD PHOTOS
Drop image files into assets/img/gallery/ and add one block per photo below.
Each block is a thumbnail that opens full-size in a lightbox when clicked.
Keep the file names simple (no spaces), e.g. baseball-2024.jpg
-->

<style>
  /* Uniform tiles: every thumbnail is cropped to the same 4:3 frame; the lightbox still opens the full photo. */
  .gallery-thumb { width: 100%; aspect-ratio: 4 / 3; object-fit: cover; object-position: 50% 30%; display: block; }
</style>

<div class="row">
{% comment %} Only the originals: the theme generates -480/-800/-1400 .webp copies of each image at build time. {% endcomment %}
{% assign gallery_images = site.static_files | where_exp: "f", "f.path contains '/assets/img/gallery/'" | where_exp: "f", "f.extname == '.jpg' or f.extname == '.jpeg' or f.extname == '.png'" | sort: "path" %}
{% if gallery_images.size == 0 %}
  <div class="col-12">
    <p class="text-muted">Photos are on their way. Check back soon!</p>
  </div>
{% endif %}
{% for f in gallery_images %}
  <div class="col-sm-6 col-md-4 mt-3">
    <a href="{{ f.path | relative_url }}" data-lightbox="gallery" data-title="{{ f.basename | replace: '-', ' ' | replace: '_', ' ' | capitalize }}">
      <img src="{{ f.path | relative_url }}" class="gallery-thumb rounded z-depth-1" alt="{{ f.basename | replace: '-', ' ' }}" loading="lazy" />
    </a>
  </div>
{% endfor %}
</div>
