---
layout: default
title: Blog
permalink: /blog
---

{% assign years = "" | split: "," %}
{% for post in site.posts %}
{% assign year = post.date | date: "%Y" %}
{% assign years = years | push: year %}
{% endfor %}
{% assign years = years | uniq | join: ", " %}

## Blog

### Posts about anything and nothing at the same time

<ul>
{% for year in years %}
<li><b>{{ year }}</b></li>
{% for post in site.posts %}
  <ul>
  {% assign postYear = post.date | date: "%Y"%}
  {% if year ==  postYear %}
    <li>{{ post.date | date: "%m.%d" }} - <a href="{{ post.url }}" class="post-preview">{{ post.title }}</a></li>
  {% endif %}
  </ul>
{% endfor%}
{% endfor %}
</ul>
