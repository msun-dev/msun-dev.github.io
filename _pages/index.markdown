---
title: Home
permalink: /
layout: default
---

## Recent posts

<ul>
  {% for post in site.posts limit:5 %}
  <li>{{ post.date | date: "%Y.%m.%d" }} - <a href="{{ post.url }}" class="post-preview">{{ post.title }}</a></li>
  {% endfor %}
  <li><a href="/blog" class="post-preview">Other posts</a></li>
</ul>

<hr>

## Projects showcase

Under construction
