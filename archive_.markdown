---
layout: page
title: Images
permalink: /archive/en/
order: 2
---

{% for image in site.static_files %}
  {% if image.path contains "archive" %}
   <img src = "{{site.baseurl}}{{image.path}}" class = "archive_img" alt = "{{image.path | split: '/' | last | split: '.' | first}}">
  {% endif %}
{% endfor %}