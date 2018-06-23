---
layout: archive
permalink: /my-portfolio/
title: "Projects done so far"
author_profile: true
header:
  image: "/images/20171112_192621.jpg" #needs a better image describing my projects
---

{% include base_path %}
{% include group-by-array collection=site.posts field="tags" %}

{% for tag in group_names %}
  {% assign posts = group_items[forloop.index0] %}
  <h2 id="{{ tag | slugify }}" class="archive__subtitle">{{ tag}}</h2>
  {% for post in posts %}
    {% include archive-single.html %}
  {% endfor %}
{% endfor %}