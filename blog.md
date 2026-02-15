---
layout: default
title: Blog
permalink: /blog/
---

<h4 class="center-align">Blog Posts</h4>

{% if site.posts.size > 0 %}
<div class="row">
{% for post in site.posts %}
    <div class="col s12">
        <div class="card hoverable">
            <div class="card-content">
                <span class="card-title"><a href="{{ post.url }}" class="blue-text text-darken-3">{{ post.title }}</a></span>
                <p class="grey-text">
                    <i class="material-icons tiny">access_time</i>
                    {{ post.date | date: "%B %d, %Y" }}
                </p>
                {% if post.excerpt %}
                <p>{{ post.excerpt | strip_html | truncatewords: 50 }}</p>
                {% endif %}
            </div>
            <div class="card-action">
                <a href="{{ post.url }}">Read more</a>
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
                <p>No blog posts yet. Check back soon!</p>
            </div>
        </div>
    </div>
</div>
{% endif %}
