---
layout: default
title: Archive
---

# Archive

Browse all posts by month and year.

{% assign postsByYearMonth = site.posts | group_by_exp: "post", "post.date | date: '%B %Y'" %}
{% for yearMonth in postsByYearMonth %}
  <h2>{{ yearMonth.name }}</h2>
  <ul>
    {% for post in yearMonth.items %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}


Browse all posts by language.
{% assign diffLang = sites.posts | group_by_exp: "post", "post.lang"%}
{% if diffLang.size > 0 %}
  {% for lang in diffLang%}
    <h2>{{ lang.name }}</h2>
    <ul>
      {% or post in lang.items %}
        <li><a href="{{post.url}}">{{ post.title }}</a></li>
      {% endfor %}
    </ul>
  {% endfor %}
{% endif %}