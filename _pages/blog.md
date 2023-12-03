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
{% assign years = years | split: ", " %}

## Blog

### Posts about anything and nothing at the same time

{% for year in years %}
<b>{{ year }}</b>
{% for post in site.posts %}

{% assign postYear = post.date | date: "%Y"%}
{% if year ==  postYear %}

<div>{{ post.date | date: "%b. %d"  }} - <a href="{{ post.url }}" class="post-preview">{{ post.title }}</a></div>
{% endif %}

{% endfor%}
{% endfor %}
