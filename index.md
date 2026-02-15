---
layout: default
title: Home
---

<div class="row">
    <div class="col s12">
        <div class="card">
            <div class="card-content center-align">
                <h5>Welcome</h5>
                <p>This is my personal space for sharing photos, thoughts, and experiments with data and technology.</p>
            </div>
        </div>
    </div>
</div>

<div class="row">
    <div class="col s12 m4">
        <div class="card hoverable">
            <div class="card-content">
                <span class="card-title">
                    <i class="material-icons left">create</i>Blog
                </span>
                <p>Essays, thoughts, and observations</p>
                {% if site.posts.size > 0 %}
                <p class="grey-text text-darken-1"><small>Latest: {{ site.posts.first.title }}</small></p>
                {% endif %}
            </div>
            <div class="card-action">
                <a href="/blog/">View all posts</a>
            </div>
        </div>
    </div>

    <div class="col s12 m4">
        <div class="card hoverable">
            <div class="card-content">
                <span class="card-title">
                    <i class="material-icons left">photo_camera</i>Photos
                </span>
                <p>Visual stories and photography</p>
                {% if site.photos.size > 0 %}
                <p class="grey-text text-darken-1"><small>{{ site.photos.size }} photo{% if site.photos.size != 1 %}s{% endif %}</small></p>
                {% endif %}
            </div>
            <div class="card-action">
                <a href="/photos/">View gallery</a>
            </div>
        </div>
    </div>

    <div class="col s12 m4">
        <div class="card hoverable">
            <div class="card-content">
                <span class="card-title">
                    <i class="material-icons left">science</i>Experiments
                </span>
                <p>Data projects and creative explorations</p>
                {% if site.experiments.size > 0 %}
                <p class="grey-text text-darken-1"><small>{{ site.experiments.size }} experiment{% if site.experiments.size != 1 %}s{% endif %}</small></p>
                {% endif %}
            </div>
            <div class="card-action">
                <a href="/experiments/">View projects</a>
            </div>
        </div>
    </div>
</div>
