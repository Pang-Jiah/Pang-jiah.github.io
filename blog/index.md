---
layout: default
title: Blog
---

# Blog

{% for post in site.posts %}
- <span class="muted">{{ post.date | date: "%Y-%m-%d" }}</span> — [{{ post.title }}]({{ post.url | relative_url }})
{% endfor %}
