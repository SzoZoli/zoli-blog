---
layout: single
title: "AI Daily hu"
permalink: /ai-daily-hu/
---

<ul>
{% assign posts = site.posts | where_exp: "p", "p.categories contains 'ai-daily-hu'" | sort: "date" | reverse %}
{% for post in posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span> — {{ post.date | date: "%Y-%m-%d" }}</span>
  </li>
{% endfor %}
</ul>
