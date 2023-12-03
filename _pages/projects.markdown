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
    <li class="project">
      <div class="project-card">
        {% if project.image %}
        <img src="{{ project.image }}" class="project-image">
        {% else %}
        <img src="assets/images/projects/noImage.png" class="project-image">
        {% endif %}
        <div class="project-text">
        <b> {{ project.name }}</b> - {{ project.type }} - {{ project.year }}
        <p> {{ project.description }}</p>
        <a href="{{ project.link }}" target="_blank">Link</a>
        {% if project.link-blog %}
         - <a href="{{ project.link-blog }}" target="_blank">Link to post</a>
        {% endif %}
        </div>
      </div>
    </li>
    {% endfor %}
</ul>
