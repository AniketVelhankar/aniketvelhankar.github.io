---
layout: default
title: "Blog"
permalink: /blog/
excerpt: "Articles and posts"
---

<div class="container" style="padding-top: 2rem;">
  <h1 style="margin-top: 0;">Blog</h1>
  <p style="color: #666; margin-bottom: 2rem;">Thoughts and articles on software engineering, technology, and building things.</p>

  {% assign posts = site.posts | sort: 'date' | reverse %}
  
  <div class="blog-posts">
    {% for post in posts %}
      <article class="blog-post-item">
        <h3>
          <a href="{{ post.url }}" style="color: #0066cc; text-decoration: none;">
            {{ post.title }}
          </a>
        </h3>
        <div class="blog-meta" style="color: #999; font-size: 0.9rem; margin-bottom: 0.75rem;">
          {% include post-date.html date=post.date %}
          {% if post.reading_time %}
            · {{ post.reading_time }} min read
          {% endif %}
        </div>
        <p>{{ post.excerpt }}</p>
      </article>
    {% endfor %}
  </div>

  {% if posts.size == 0 %}
    <p style="color: #999; text-align: center; margin-top: 3rem;">No posts published yet. Check back soon.</p>
  {% endif %}
</div>

<style>
  .blog-posts {
    margin-top: 2rem;
  }

  .blog-post-item {
    padding: 1.5rem 0;
    border-bottom: 1px solid #e0e0e0;
  }

  .blog-post-item:last-child {
    border-bottom: none;
  }

  .blog-post-item h3 {
    margin: 0 0 0.5rem;
    font-size: 1.3rem;
  }

  .blog-post-item a {
    color: #0066cc;
    text-decoration: none;
    transition: color 0.2s;
  }

  .blog-post-item a:hover {
    color: #0052a3;
    text-decoration: underline;
  }

  .blog-meta {
    margin-bottom: 0.75rem;
  }

  .blog-post-item p {
    margin: 0;
    line-height: 1.6;
  }

  @media (max-width: 768px) {
    .blog-post-item h3 {
      font-size: 1.1rem;
    }

    .blog-post-item {
      padding: 1.25rem 0;
    }
  }
</style>
