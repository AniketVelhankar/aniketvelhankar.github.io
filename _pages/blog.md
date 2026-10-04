---
layout: default
title: "Blog"
permalink: /blog/
excerpt: "Articles and posts"
---

<div class="container listing-page">
  <header class="listing-intro">
    <h1>Blog</h1>
    <p>Thoughts and articles on software engineering, technology, and building things.</p>
  </header>

  {% assign posts = site.posts | sort: 'date' | reverse %}

  <div class="blog-posts">
    {% for post in posts %}
      <article class="blog-post-item">
        <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
        <p class="blog-meta">
          {% include post-date.html date=post.date %}
          {% if post.reading_time %}
            · {{ post.reading_time }} min read
          {% endif %}
        </p>
        <p class="blog-post-item__excerpt">{{ post.excerpt | strip_html | strip }}</p>
      </article>
    {% endfor %}
  </div>

  {% if posts.size == 0 %}
    <p class="blog-empty">No posts published yet.</p>
  {% endif %}
</div>
