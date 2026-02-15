---
layout: default
title: Experiments
permalink: /experiments/
---

# Experiments

{% if site.experiments.size > 0 %}
<div class="experiments-list">
{% for experiment in site.experiments %}
    <article class="experiment-item">
        <h2><a href="{{ experiment.url }}">{{ experiment.title }}</a></h2>
        {% if experiment.description %}
        <p class="experiment-description">{{ experiment.description }}</p>
        {% endif %}
        {% if experiment.tags %}
        <div class="experiment-tags">
            {% for tag in experiment.tags %}
            <span class="tag">{{ tag }}</span>
            {% endfor %}
        </div>
        {% endif %}
    </article>
{% endfor %}
</div>
{% else %}
<p class="no-content">Experiments will appear here as I work on new projects and ideas.</p>
{% endif %}

<style>
    .experiments-list {
        margin-top: 2rem;
    }

    .experiment-item {
        margin-bottom: 2rem;
        padding: 1.5rem;
        background-color: #f8f9fa;
        border-radius: 8px;
        border-left: 4px solid #3498db;
    }

    .experiment-item h2 {
        margin-top: 0;
        margin-bottom: 0.5rem;
    }

    .experiment-item h2 a {
        color: #2c3e50;
        text-decoration: none;
    }

    .experiment-item h2 a:hover {
        color: #3498db;
    }

    .experiment-description {
        color: #555;
        line-height: 1.6;
        margin-bottom: 1rem;
    }

    .experiment-tags {
        margin-top: 1rem;
    }

    .tag {
        display: inline-block;
        background-color: #e0e0e0;
        padding: 0.25rem 0.75rem;
        margin: 0.25rem 0.25rem 0.25rem 0;
        border-radius: 3px;
        font-size: 0.85rem;
        color: #555;
    }

    .no-content {
        text-align: center;
        color: #999;
        font-style: italic;
        padding: 3rem 0;
    }
</style>
