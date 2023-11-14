---
layout: page
title: Beeldarchief
permalink: /archive/
order: 2
---

{% for image in site.static_files %}
{% if image.path contains "archive" %}
![img]({{site.baseurl}}{{image.path}})
{% endif %}
{% endfor %}