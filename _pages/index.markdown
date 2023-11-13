---
title: Home
permalink: /
layout: default
---

## About me

## Recent posts

<ul>
  {% for post in site.posts limit:5 %}
  <li><a href="{{ post.url }}" class="post-preview">{{ post.date | date: "%Y.%m.%d" }} - {{ post.title }}</a></li>
  {% endfor %}
  <li><a href="/blog" class="post-preview">Other posts</a></li>
</ul>

<hr>

## Projects showcase

Under construction
