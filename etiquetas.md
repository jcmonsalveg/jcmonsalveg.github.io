---
layout: page
title: Etiquetas
permalink: /etiquetas/
order: 2
---

{% for tag in site.tags %}
  <h3>{{ tag[0] }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ post.url }}">{{ post.title }} | {{ post.date | date: "%-d %B %Y" }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
