---
title: Home
permalink: /
layout: default
---

## Hello!

Doing things and writing about it.<br>
Have fun exploring!

<hr>

## Recent posts

<ul class="posts">
{% for post in site.posts limit:5 %}
  <li>{{ post.date | date: "%Y %b. %d"  }} - <a href="{{ post.url }}" class="post-preview">{{ post.title }}</a></li>
{% endfor %}
</ul>
<div><center><a href="/blog">Other posts</a></center></div>

<hr>

## Recent projects

<ul class="projects">
    {% for project in site.data.projects limit:3%}
    <li>
      <div class="project-card">
        {% if project.image %}
        <img src="{{ project.image }}" class="project-image">
        {% else %}
        <img src="assets/images/projects/noImage.png" class="project-image">
        {% endif %}
        <div class="project-text">
        <b> {{ project.name }}</b> 
        <p> {{ project.year }} - {{ project.type }} </p> 
        <p> {{ project.description }}</p>
        {% if project.link %}
          <a href="{{ project.link }}" target="_blank">Link</a>
        {% else %}
          <b>WIP</b>
        {% endif %}
        {% if project.link-blog %}
         - <a href="{{ project.link-blog }}" target="_blank">Link to post</a>
        {% endif %}
        </div>
      </div>
    </li>
    {% endfor %}
    <center><a href="/projects">Other projects</a></center>
</ul>
