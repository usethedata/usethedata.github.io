---
layout: default
title: Photos
permalink: /photos/
---

<h4 class="center-align">Photo Gallery</h4>

{% if site.photos.size > 0 %}
<div class="row">
{% for photo in site.photos %}
    <div class="col s12 m6 l4">
        <div class="card hoverable">
            {% if photo.thumbnail %}
            <div class="card-image">
                <img src="{{ photo.thumbnail }}" alt="{{ photo.title }}">
            </div>
            {% else %}
            <div class="card-image" style="background-color: #e0e0e0; height: 250px; display: flex; align-items: center; justify-content: center;">
                <i class="material-icons large grey-text">photo_camera</i>
            </div>
            {% endif %}
            <div class="card-content">
                <span class="card-title">{{ photo.title }}</span>
                {% if photo.date %}
                <p class="grey-text">
                    <i class="material-icons tiny">access_time</i>
                    {{ photo.date | date: "%B %Y" }}
                </p>
                {% endif %}
            </div>
            <div class="card-action">
                <a href="{{ photo.url }}">View photo</a>
            </div>
        </div>
    </div>
{% endfor %}
</div>
{% else %}
<div class="row">
    <div class="col s12">
        <div class="card">
            <div class="card-content center-align grey-text">
                <i class="material-icons large">photo_library</i>
                <p>Photo gallery coming soon!</p>
            </div>
        </div>
    </div>
</div>
{% endif %}
