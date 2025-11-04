---
layout: page
permalink: /repositories/
title: repositories
description: GitHub repositories by Paolo Gajo.
nav: true
nav_order: 4
---

{% assign github_users = "paolo-gajo" | split: "," %}
{% assign github_repos = "TinfFoil/natcode-llm-kgc, paolo-gajo/EfficientSDP, paolo-gajo/MNIST_Tutorial, paolo-gajo/LEARN, paolo-gajo/subtitling" | split: ", " %}

{% if github_users %}

## GitHub users

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in github_users %}
    {% include repository/repo_user.liquid username=user %}
  {% endfor %}
</div>

---

{% if site.repo_trophies.enabled %}
{% for user in github_users %}
{% if github_users.size > 1 %}
  <h4>{{ user }}</h4>
{% endif %}
  <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
    {% include repository/repo_trophies.liquid username=user %}
  </div>
---
{% endfor %}
{% endif %}
{% endif %}

{% if github_repos %}

## GitHub Repositories

<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
{% endif %}
