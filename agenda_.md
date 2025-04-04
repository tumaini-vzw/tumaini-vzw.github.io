---
layout: page
title: Agenda
permalink: /agenda/en/
order: 1
---

### Planned events
---
<br>

<div id = "planned" markdown = "1">

  <ul class="post-list">
    {%- for post in site.categories.agenda -%}
      <li>
        {%- assign date_format = site.minima.date_format | default: "%-d %b, %Y" -%}
        {%- assign now = 'now' | date: "%s" -%}
        {%- assign post_time = post.date | date: "%s" -%}
        {%- assign diff = now | minus: post_time | divided_by: 3600 | divided_by: 24 -%}
        {%- if diff <= 0 -%}
          {%- assign flag = true -%}
            <span class="post-meta">{{ post.date | date: date_format }}</span>
            <h3>
              <a class="post-link" href="{{ post.url | relative_url }}">
                {{ post.title | escape }}
              </a>
            </h3>
            {{ post.excerpt }}
        {%- endif -%}
      </li>
    {%- endfor -%}
    {%- if flag != true -%}
      <br>
      <br>
    {%- endif -%}
  </ul>
</div>


### Past events
---
<br>

<ul class="post-list">
  {%- for post in site.categories.agenda -%}
    {%- assign date_format = site.minima.date_format | default: "%-d %b, %Y" -%}
    {%- assign now = 'now' | date: "%s" -%}
    {%- assign post_time = post.date | date: "%s" -%}
    {%- assign diff = now | minus: post_time | divided_by: 3600 | divided_by: 24 -%}
    {%- if diff > 0 -%}
      <li>
        <span class="post-meta">{{ post.date | date: date_format }}</span>
        <h3>
          <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a>
        </h3>
      </li>
    {%- endif -%}
  {%- endfor -%}
</ul>