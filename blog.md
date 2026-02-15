---
layout: default
title: Blog
permalink: /blog/
---

# Blog Posts

{% if site.posts.size > 0 %}
<div class="post-list">
{% for post in site.posts %}
    <article class="post-preview">
        <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
        <p class="post-date">{{ post.date | date: "%B %d, %Y" }}</p>
        {% if post.excerpt %}
        <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 50 }}</p>
        {% endif %}
        <a href="{{ post.url }}" class="read-more">Read more →</a>
    </article>
{% endfor %}
</div>
{% else %}
<p class="no-content">No blog posts yet. Check back soon!</p>
{% endif %}

<style>
    .post-list {
        margin-top: 2rem;
    }

    .post-preview {
        margin-bottom: 3rem;
        padding-bottom: 2rem;
        border-bottom: 1px solid #e0e0e0;
    }

    .post-preview:last-child {
        border-bottom: none;
    }

    .post-preview h2 {
        margin-top: 0;
        margin-bottom: 0.5rem;
    }

    .post-preview h2 a {
        color: #2c3e50;
        text-decoration: none;
    }

    .post-preview h2 a:hover {
        color: #3498db;
    }

    .post-date {
        color: #666;
        font-size: 0.9rem;
        margin-bottom: 1rem;
    }

    .post-excerpt {
        color: #444;
        line-height: 1.6;
    }

    .read-more {
        color: #3498db;
        text-decoration: none;
        font-weight: 500;
    }

    .read-more:hover {
        text-decoration: underline;
    }

    .no-content {
        text-align: center;
        color: #999;
        font-style: italic;
        padding: 3rem 0;
    }
</style>
