---
layout: single
title: "AI Daily en"
permalink: /ai-daily-en/
---

<ul>
{% assign posts = site.posts | where_exp: "p", "p.categories contains 'ai-daily-en'" | sort: "date" | reverse %}
{% for post in posts %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <span> — {{ post.date | date: "%Y-%m-%d" }}</span>
  </li>
{% endfor %}
</ul>
