---
title: Home
permalink: /
layout: default
---

## Recent posts

<ul>
  {% for post in site.posts limit:5 %}
  <li>{{ post.date | date: "%Y-%m-%d" }} - <a href="{{ post.url }}" class="post-preview"  target="_blank">{{ post.title }}</a></li>
  {% endfor %}
</ul>
<center><a href="/blog">Other posts</a></center>

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
    <center><a href="/projects">Other projects</a></center>
</ul>

<script>
  console.log("And?");
</script>
