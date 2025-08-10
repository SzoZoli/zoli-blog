---
layout: collection
title: "AI Daily hu"
permalink: /ai-daily-hu/
author_profile: false
collection: ai-daily-hu
entries_layout: list
---

{% assign sorted = site.ai-daily-hu | sort: 'date' | reverse %}
{% for post in sorted %}
  <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
  <p>{{ post.excerpt | strip_html | truncate: 200 }}</p>
{% endfor %}
