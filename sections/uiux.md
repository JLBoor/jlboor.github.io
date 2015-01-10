---
layout: page
title: UI/UX Articles
excerpt: "UI/UX articles sorted by date."
index:
  image: uiux.png
---

<ul class="post-list">
{% for post in site.categories.uiux %}
  {% if post.tags contains "frontend" %}
  <li><article><a href="{{ site.url }}{{ post.url }}">{{ post.title }} <span class="entry-date"><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time></span></a></article></li>
  {% endif %}
{% endfor %}
</ul>
