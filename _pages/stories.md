---
layout: category
title: Contributor Stories
permalink: /stories/index.html
---

This is a test

{% for story in site.stories %}
  <h2>{{ story.name }}</h2>
  <p>{{ story.content | markdownify }}</p>
{% endfor %}

