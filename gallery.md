---
layout: single
permalink: /gallery/
title: "Gallery"
author_profile: true
classes: wide
---

<style>
  .photo-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 1em;
  }
  .photo-grid figure {
    margin: 0;
  }
  .photo-grid a {
    display: block;
    aspect-ratio: 4 / 3;
    overflow: hidden;
    border-radius: 4px;
  }
  .photo-grid figcaption {
    margin-top: 0.4em;
  }
  .photo-grid img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.3s ease;
  }
  .photo-grid a:hover img {
    transform: scale(1.05);
  }
</style>

{% comment %}
  Every image in /assets/images/gallery/ is shown automatically, sorted by file name.
  Captions are read from _data/gallery.yml.
{% endcomment %}
{% assign image_exts = ".jpg,.jpeg,.png,.gif,.webp" | split: "," %}
{% assign photos = site.static_files | where_exp: "file", "file.path contains '/assets/images/gallery/'" | sort: "name" %}

<div class="photo-grid">
{% for photo in photos %}
  {% assign ext = photo.extname | downcase %}
  {% if image_exts contains ext %}
  {% assign caption = site.data.gallery[photo.name] %}
  <figure>
    <a href="{{ photo.path | relative_url }}" target="_blank">
      <img src="{{ photo.path | relative_url }}" alt="{{ caption | default: photo.basename }}" loading="lazy">
    </a>
    {% if caption %}<figcaption>{{ caption }}</figcaption>{% endif %}
  </figure>
  {% endif %}
{% endfor %}
</div>
