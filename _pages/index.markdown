---
title: Home
permalink: /
layout: default
---

## Recent posts

<ul>
  {% for post in site.posts limit:5 %}
  <li>{{ post.date | date: "%Y-%m-%d" }} - <a href="{{ post.url }}" class="post-preview">{{ post.title }}</a></li>
  {% endfor %}
  <li><a href="/blog" class="post-preview">Other posts</a></li>
</ul>

## Recent projects

<ul class="projects">
    {% for project in site.data.projects limit:3%}
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
    <!-- <li><a href="/blog" class="post-preview">Other projects</a></li> -->
</ul>
