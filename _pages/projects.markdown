---
layout: default
title: Projects
permalink: /projects
is_post: false
---

## Projects showcase

### Showcase-worthy projects starting from year 2021

<ul class="projects">
    {% for project in site.data.projects %}
    <li>
      <div class="project-card">
        {% if project.image %}
        <img src="{{ project.image }}">
        {% else %}
        <img src="assets/images/projects/noImage.png">
        {% endif %}
        <div class="project-text">
        <b> {{ project.name }}</b> - {{ project.type }} - {{ project.year }} - <a href="{{ project.link }}">Link</a><br>
        <p> {{ project.description }}</p>
        </div>
      </div>
    </li>
    {% endfor %}
</ul>
