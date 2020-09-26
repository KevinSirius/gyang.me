---
layout: default
title: Archive
---

# Archive

<br />
## Browse all posts by month and year.

{% assign postsByYearMonth = site.posts | group_by_exp: "post", "post.date | date: '%B %Y'" %}
{% for yearMonth in postsByYearMonth %}
  <h2>{{ yearMonth.name }}</h2>
  <ul>
    {% for post in yearMonth.items %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}

<br />

## Browse all posts by language.

{% assign postsByLanguage = site.posts | group_by_exp: "post", "post.lang"%}
{% for language in postsByLanguage %}
  <h2> {{ language.name }}</h2>
  <ul>
    {% for post in language.items %}
      <li><a href="{{ post.url}}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}

