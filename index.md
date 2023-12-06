---
layout: default
title: My GitHub Repositories
---

# My GitHub Repositories

{% for repo in site.github.public_repositories %}
  <div class="repo-item">
    <h3 class="repo-name">
      <a href="{{ repo.html_url }}" target="_blank">{{ repo.name }}</a>
    </h3>
    <p class="repo-description">{{ repo.description | default: 'No description provided.' }}</p>
  </div>
{% endfor %}
