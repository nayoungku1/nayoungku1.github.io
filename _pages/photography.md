---
layout: archive
title: "Photography"
permalink: /photography/
author_profile: true
---

{% include base_path %}

<style>
  .photo-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
    gap: 0.6em;
    margin: 1em 0 2em;
  }
  .photo-thumb {
    display: block;
    aspect-ratio: 1 / 1;
    overflow: hidden;
    border-radius: 4px;
    background: #eee;
  }
  .photo-thumb img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    transition: transform 0.25s ease;
  }
  .photo-thumb:hover img { transform: scale(1.04); }
  .photo-thumb { position: relative; }
  .photo-badge {
    position: absolute;
    left: 0.4em;
    bottom: 0.4em;
    padding: 0.05em 0.5em;
    font-size: 0.7em;
    letter-spacing: 0.04em;
    color: #fff;
    background: rgba(0, 0, 0, 0.55);
    border-radius: 999px;
  }

  /* CSS-only lightbox: opens via the #photo-... anchor, closes by clicking anywhere */
  .photo-lightbox {
    display: none;
    position: fixed;
    inset: 0;
    z-index: 9999;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 1em;
    background: rgba(0, 0, 0, 0.9);
    color: #fff;
    text-align: center;
  }
  .photo-lightbox:target { display: flex; }
  .photo-lightbox img {
    max-width: 94vw;
    max-height: 78vh;
    object-fit: contain;
  }
  .photo-lightbox .photo-title { margin-top: 0.8em; font-weight: 600; }
  .photo-lightbox .photo-meta,
  .photo-lightbox .photo-caption { font-size: 0.85em; opacity: 0.85; max-width: 40em; }
</style>

{% assign photos = site.data.photography | sort: "date" | reverse %}

{% if photos.size == 0 %}

Photographs are coming soon.

{% else %}

{% assign albums = photos | group_by: "album" %}
{% for album in albums %}
  {% if album.name != "" %}
<h2>{{ album.name }}</h2>
<hr>
  {% endif %}
<div class="photo-grid">
  {% for photo in album.items %}
    {% assign pid = photo.file | slugify %}
  <a class="photo-thumb" href="#photo-{{ pid }}" title="{{ photo.title }}">
    <img src="{{ base_path }}/images/photography/{{ photo.thumb | default: photo.file }}" alt="{{ photo.alt | default: photo.title }}" loading="lazy">
    {% if photo.film %}<span class="photo-badge">Film</span>{% endif %}
  </a>
  {% endfor %}
</div>
  {% for photo in album.items %}
    {% assign pid = photo.file | slugify %}
<a class="photo-lightbox" id="photo-{{ pid }}" href="#_">
  <img src="{{ base_path }}/images/photography/{{ photo.file }}" alt="{{ photo.alt | default: photo.title }}" loading="lazy">
  <span class="photo-title">{{ photo.title }}</span>
  {% capture photo_meta %}{% if photo.film %}{% if photo.film == true %}Film{% else %}Film, {{ photo.film }}{% endif %}|{% endif %}{% if photo.camera %}{{ photo.camera }}|{% endif %}{% if photo.location %}{{ photo.location }}|{% endif %}{% if photo.date %}{{ photo.date | date: "%b %Y" }}|{% endif %}{% endcapture %}
  {% assign meta_parts = photo_meta | split: "|" %}
  {% if meta_parts.size > 0 %}<span class="photo-meta">{{ meta_parts | join: " · " }}</span>{% endif %}
  {% if photo.caption %}<span class="photo-caption">{{ photo.caption }}</span>{% endif %}
</a>
  {% endfor %}
{% endfor %}

{% endif %}
