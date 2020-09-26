---
layout: default
title: Coding Stuff
---

# All Posts about Tech


{% assign postsByCategory = site.posts | group_by_exp: "post", "post.theme" %}
{% for theme in postsByCategory %}
  {% if theme.name == "tech" %}
  <ul>
      {% for post in theme.items %}
        <li><a href="{{ post.url }}">{{ post.title }} - {{ post.date | date: '%B %Y'}}</a></li>
      {% endfor %}
  </ul>
  {% endif %}
{% endfor %}



