---
layout: default
title: Photos
permalink: /photos/
---

# Photos

{% if site.photos.size > 0 %}
<div class="photo-grid">
{% for photo in site.photos %}
    <div class="photo-item">
        <a href="{{ photo.url }}">
            {% if photo.thumbnail %}
            <img src="{{ photo.thumbnail }}" alt="{{ photo.title }}">
            {% else %}
            <div class="photo-placeholder">📷</div>
            {% endif %}
            <h3>{{ photo.title }}</h3>
        </a>
        {% if photo.date %}
        <p class="photo-date">{{ photo.date | date: "%B %Y" }}</p>
        {% endif %}
    </div>
{% endfor %}
</div>
{% else %}
<p class="no-content">Photo gallery coming soon!</p>
{% endif %}

<style>
    .photo-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
        gap: 2rem;
        margin-top: 2rem;
    }

    .photo-item {
        text-align: center;
    }

    .photo-item a {
        text-decoration: none;
        color: inherit;
    }

    .photo-item img {
        width: 100%;
        height: 250px;
        object-fit: cover;
        border-radius: 8px;
        transition: transform 0.2s;
    }

    .photo-item img:hover {
        transform: scale(1.05);
    }

    .photo-placeholder {
        width: 100%;
        height: 250px;
        background-color: #f0f0f0;
        border-radius: 8px;
        display: flex;
        align-items: center;
        justify-content: center;
        font-size: 4rem;
    }

    .photo-item h3 {
        margin: 1rem 0 0.5rem 0;
        font-size: 1.1rem;
        color: #2c3e50;
    }

    .photo-date {
        color: #666;
        font-size: 0.85rem;
        margin: 0;
    }

    .no-content {
        text-align: center;
        color: #999;
        font-style: italic;
        padding: 3rem 0;
    }
</style>
