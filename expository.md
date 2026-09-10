---
layout: default
title: Expository
permalink: /expository/
---

# Expository articles

Here you can find some of my writings...

{% for post in site.expository_posts %}
  <article>
    <h2>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h2>

    <p>
      <small>{{ post.date | date: "%B %-d, %Y" }}</small>
    </p>

    <p>{{ post.excerpt }}</p>
  </article>
{% endfor %}