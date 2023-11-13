---
layout: default
title: Blog
permalink: /blog
---

## Blog

### Posts about anything and nothing at the same time

<hr>

<ul>
  {% for post in site.posts %}
  <li><a href="{{ post.url }}" class="post-preview">{{ post.title }}</a></li>
  {% endfor %}
</ul>
