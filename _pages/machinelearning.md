---
layout: posts
permalink: /data-cleaning/
title: "Data Cleaning Projects"
author_profile: true
header:
  image: "/images/fort point.png"
---
{% include base_path %}
{% include group-by-array collection=site.posts fields="tags" %}

{% for tag in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ tag | slugify }}" class="archive__subtitle">{{ tag }}</h2>
  {% for posts in posts %}
    { % include archive-single.html %}
  {% endfor %}
{% endfor %}
