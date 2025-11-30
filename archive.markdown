---
layout: page
title: Beeldarchief
permalink: /archive/
order: 2
---

<div id = "galleryContainer">
<div id = "gallery">
{% for image in site.static_files %}
{% if image.path contains "archive" %}
<img src = "{{site.baseurl}}{{image.path}}" class = "archive_img" alt = "{{image.path | split: '/' | last | split: '.' | first}}">
{% endif %}
{% endfor %}
</div>
</div>