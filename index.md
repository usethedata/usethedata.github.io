---
layout: default
title: Home
---

<div class="intro">
    <h2>Welcome</h2>
    <p>This is my personal space for sharing photos, thoughts, and experiments with data and technology.</p>
</div>

<section class="content-sections">
    <div class="section-card">
        <h3><a href="/blog/">📝 Blog</a></h3>
        <p>Essays, thoughts, and observations</p>
        {% if site.posts.size > 0 %}
        <p class="section-meta">Latest: <a href="{{ site.posts.first.url }}">{{ site.posts.first.title }}</a></p>
        {% endif %}
    </div>

    <div class="section-card">
        <h3><a href="/photos/">📷 Photos</a></h3>
        <p>Visual stories and photography</p>
        {% if site.photos.size > 0 %}
        <p class="section-meta">{{ site.photos.size }} photo{{ site.photos.size | plus: 0 | divided_by: 1 | plus: 1 | divided_by: 2 | plus: 0 | times: 0 | plus: site.photos.size }}{% if site.photos.size != 1 %}s{% endif %}</p>
        {% endif %}
    </div>

    <div class="section-card">
        <h3><a href="/experiments/">🧪 Experiments</a></h3>
        <p>Data projects and creative explorations</p>
        {% if site.experiments.size > 0 %}
        <p class="section-meta">{{ site.experiments.size }} experiment{{ site.experiments.size | plus: 0 | divided_by: 1 | plus: 1 | divided_by: 2 | plus: 0 | times: 0 | plus: site.experiments.size }}{% if site.experiments.size != 1 %}s{% endif %}</p>
        {% endif %}
    </div>
</section>

<style>
    .intro {
        text-align: center;
        margin-bottom: 3rem;
        padding: 2rem 0;
        border-bottom: 2px solid #2c3e50;
    }

    .intro h2 {
        margin-top: 0;
        color: #2c3e50;
    }

    .content-sections {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
        gap: 2rem;
        margin-top: 2rem;
    }

    .section-card {
        padding: 1.5rem;
        background-color: #f8f9fa;
        border-radius: 8px;
        transition: transform 0.2s, box-shadow 0.2s;
    }

    .section-card:hover {
        transform: translateY(-4px);
        box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    }

    .section-card h3 {
        margin-top: 0;
        margin-bottom: 0.5rem;
    }

    .section-card h3 a {
        color: #2c3e50;
        text-decoration: none;
    }

    .section-card h3 a:hover {
        color: #3498db;
    }

    .section-card p {
        margin-bottom: 0.5rem;
        color: #666;
    }

    .section-meta {
        font-size: 0.85rem;
        font-style: italic;
        color: #888;
    }

    .section-meta a {
        color: #3498db;
        text-decoration: none;
    }

    .section-meta a:hover {
        text-decoration: underline;
    }
</style>
