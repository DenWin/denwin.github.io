---
title: Tagcloud
layout: default
tags:
- Jekyll
- Tagcloud
---

## Version 1

{% assign tags = site.tags | sort %}
{% for tag in tags %}
 <span class="site-tag">
    <a href="/tag/{{ tag | first | slugify }}/"
        style="font-size: {{ tag | last | size  |  times: 4 | plus: 80  }}%">
            {{ tag[0] | replace:'-', ' ' }} ({{ tag | last | size }})
    </a>
</span>
{% endfor %}

## Version 2

{% for tag in site.tags %}
  Name: {{ tag | first }},
  count: {{ tag | last | size}}
{% endfor %}