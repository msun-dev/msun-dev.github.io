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
        <img src="{{ project.image }}">
        {% else %}
        <img src="assets/images/projects/noImage.png">
        {% endif %}
        <div class="project-text">
        <b> {{ project.name }}</b> - {{ project.type }} - {{ project.year }}
        <p> {{ project.description }}</p>
        <a href="{{ project.link }}">Link</a>
        {% if project.link-blog %}
         - <a href="{{ project.link-blog }}">Link to post</a>
        {% endif %}
        </div>
      </div>
    </li>
    {% endfor %}
    <li><a href="/blog" class="post-preview">Other projects</a></li> 
</ul>
