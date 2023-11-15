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
    <a href="/blog" class="post-preview" style="position :center">Other projects</a>
</ul>
