---
layout: default
title: Life Stuff
---

# All Things Other Than Tech


{% assign postsByCategory = site.posts | group_by_exp: "post", "post.theme" %}
{% for theme in postsByCategory %}
  {% if theme.name == "life" %}
  <ul>
      {% for post in theme.items %}
        <li><a href="{{ post.url }}">{{ post.title }} - {{ post.date | date: '%B %Y'}}</a></li>
      {% endfor %}
  </ul>
  {% endif %}
{% endfor %}



