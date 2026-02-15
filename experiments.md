---
layout: default
title: Experiments
permalink: /experiments/
---

<h4 class="center-align">Experiments</h4>

{% if site.experiments.size > 0 %}
<div class="row">
{% for experiment in site.experiments %}
    <div class="col s12">
        <div class="card hoverable">
            <div class="card-content">
                <span class="card-title">
                    <a href="{{ experiment.url }}" class="blue-text text-darken-3">{{ experiment.title }}</a>
                </span>
                {% if experiment.description %}
                <p>{{ experiment.description }}</p>
                {% endif %}
                {% if experiment.tags %}
                <div class="chips">
                    {% for tag in experiment.tags %}
                    <div class="chip">{{ tag }}</div>
                    {% endfor %}
                </div>
                {% endif %}
            </div>
            <div class="card-action">
                <a href="{{ experiment.url }}">View project</a>
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
                <i class="material-icons large">science</i>
                <p>Experiments will appear here as I work on new projects and ideas.</p>
            </div>
        </div>
    </div>
</div>
{% endif %}
