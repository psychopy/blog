---
layout: categories
title: Contributor Stories
permalink: /categories/index.html
---

This is a test

{% for story in site.stories %}
  <h2>{{ story.name }}</h2>
  <p>{{ story.content | markdownify }}</p>
{% endfor %}

