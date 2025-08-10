---
layout: collection
title: "AI Daily en"
permalink: /ai-daily-en/
author_profile: false
collection: ai-daily-en
entries_layout: list
---

{% assign sorted = site.ai-daily-en | sort: 'date' | reverse %}
{% for post in sorted %}
  <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
  <p>{{ post.excerpt | strip_html | truncate: 200 }}</p>
{% endfor %}
