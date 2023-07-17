---
layout: post_markdown
title: Adding Tags to Posts on GitHub Pages
description: How to use Jekyll tags on GitHub Pages blogs.
tags:
- Jekyll
- GitHub Pages
- Blog
---

## Version 1 - page tags

{% for tag in page.tags %}
    {{ tag }}
{% endfor %}

## Version 1 - site tags

{% assign tags = site.tags | sort %}
{% for tag in tags %}
 <span class="site-tag">
    <a href="/tag/{{ tag | first | slugify }}/"
        style="font-size: {{ tag | last | size  |  times: 4 | plus: 80  }}%">
            {{ tag[0] | replace:'-', ' ' }} ({{ tag | last | size }})
    </a>
</span>
{% endfor %}

## Version 2 - site tags

{% for tag in site.tags %}
  Name: {{ tag | first }},
  count: {{ tag | last | size}}
{% endfor %}

## sorting

{% capture _site_tags %}{% for tag in site.tags %}{{ tag | first }}{% unless forloop.last %}###{% endunless %}{% endfor %}{% endcapture %}

{% assign tags_alphabetically_sorted = _site_tags | split:'###' | sort %}