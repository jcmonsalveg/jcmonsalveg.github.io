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
      <li><a href="{{ post.url }}">{{ post.title }} | {{ post.date | date_to_long_string: "ordinal" }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
 -----
 {{ site.tags }}