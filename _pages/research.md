---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

{% include base_path %}

Publications
======

{% for post in site.publications reversed %}
* {{ post.title }}. {% if post.venue %}{{ post.venue }}, {% endif %}{{ post.date | default: "1900-01-01" | date: "%Y" }}.
{% endfor %}

Talks
======

{% for post in site.talks reversed %}
* {{ post.title }}. {% if post.type %}{{ post.type }}, {% endif %}{% if post.venue %}{{ post.venue }}, {% endif %}{{ post.date | default: "1900-01-01" | date: "%Y" }}.
{% endfor %}
