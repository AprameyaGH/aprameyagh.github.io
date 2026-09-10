---
layout: default
title: Expository
permalink: /expository/
---

# Expository

Here you can find some of my writings which are more expository in nature, or updates about my research ...

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