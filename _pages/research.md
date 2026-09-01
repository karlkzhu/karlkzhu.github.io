---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
sitemap: true
---

{% include base_path %}

{% assign sorted_publications = site.publications | sort: "date" | reverse %}

## Publications

{% assign publications = sorted_publications | where: "status", "publication" %}
{% assign conference_proceedings = sorted_publications | where: "status", "conference-proceedings" %}
{% assign published_work = publications | concat: conference_proceedings %}
{% if published_work.size > 0 %}
<ul class="publication-list">
{% for post in published_work %}
  <li>
    <strong>
      {% if post.paperurl %}
        <a href="{{ post.paperurl }}">{{ post.title }}</a>
      {% else %}
        {{ post.title }}
      {% endif %}
    </strong><br>
    {% if post.authors %}{% assign authors = post.authors | replace: "Karl Zhu", "<strong>Karl Zhu</strong>" %}{{ authors }}.<br>{% endif %}
    {% if post.venue or post.date %}{% if post.venue %}<em>{{ post.venue }}</em>{% endif %}{% if post.venue and post.date %}, {% endif %}{% if post.date %}{{ post.date | date: "%Y" }}{% endif %}.{% endif %}
  </li>
{% endfor %}
</ul>
{% endif %}

{% assign manuscripts_under_review = sorted_publications | where: "status", "under-review" %}
{% if manuscripts_under_review.size > 0 %}
## Manuscripts Under Review

<ul class="publication-list">
{% for post in manuscripts_under_review %}
  <li>
    <strong>
      {% if post.paperurl %}
        <a href="{{ post.paperurl }}">{{ post.title }}</a>
      {% else %}
        {{ post.title }}
      {% endif %}
    </strong><br>
    {% if post.authors %}{% assign authors = post.authors | replace: "Karl Zhu", "<strong>Karl Zhu</strong>" %}{{ authors }}.<br>{% endif %}
    {% if post.venue or post.date %}{% if post.venue %}<em>{{ post.venue }}</em>{% endif %}{% if post.venue and post.date %}, {% endif %}{% if post.date %}{{ post.date | date: "%Y" }}{% endif %}.{% endif %}
  </li>
{% endfor %}
</ul>
{% endif %}

{% assign working_papers = sorted_publications | where: "status", "working-paper" %}
{% if working_papers.size > 0 %}
## Working Papers

<ul class="publication-list">
{% for post in working_papers %}
  <li>
    <strong>
      {% if post.paperurl %}
        <a href="{{ post.paperurl }}">{{ post.title }}</a>
      {% else %}
        {{ post.title }}
      {% endif %}
    </strong><br>
    {% if post.authors %}{% assign authors = post.authors | replace: "Karl Zhu", "<strong>Karl Zhu</strong>" %}{{ authors }}.<br>{% endif %}
    {% if post.venue or post.date %}{% if post.venue %}<em>{{ post.venue }}</em>{% endif %}{% if post.venue and post.date %}, {% endif %}{% if post.date %}{{ post.date | date: "%Y" }}{% endif %}.{% endif %}
  </li>
{% endfor %}
</ul>
{% endif %}
