---
permalink: /
title: "Aniket Velhankar"
excerpt: "Software engineer at HSBC working across backend engineering, platform engineering, and distributed systems."
layout: splash
redirect_from:
  - /about/
  - /about.html
---

<div class="home-page">
  <header class="home-intro">
    <p class="home-kicker">Software Engineer</p>
    <h1>Aniket Velhankar</h1>
    <p class="home-lead">I build backend systems and platforms, with a focus on reliability, distributed systems, and thoughtful engineering.</p>
    <p class="home-summary">I currently work at HSBC as a Consultant Specialist in Investment Banking, designing solutions for complex banking systems. My interests include backend engineering, platform engineering, and system design.</p>
    <ul class="home-links" aria-label="Contact and profiles">
      <li><a href="mailto:{{ site.author.email }}">Email</a></li>
      <li><a href="https://github.com/{{ site.author.github }}">GitHub</a></li>
      <li><a href="https://www.linkedin.com/in/{{ site.author.linkedin }}/">LinkedIn</a></li>
    </ul>
  </header>

  <section class="home-writing" aria-labelledby="home-writing-title">
    <div class="home-section-heading">
      <h2 id="home-writing-title">Recent writing</h2>
      <a href="{{ base_path }}/blog/">All writing</a>
    </div>
    {% assign recent_posts = site.posts | sort: 'date' | reverse %}
    {% if recent_posts.size > 0 %}
      <ul class="home-writing-list">
        {% for post in recent_posts limit:3 %}
          <li>
            <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y" }}</time>
            <a href="{{ post.url }}">{{ post.title }}</a>
          </li>
        {% endfor %}
      </ul>
    {% else %}
      <p class="home-empty">New writing will appear here.</p>
    {% endif %}
  </section>

  <p class="home-more">Browse <a href="{{ base_path }}/papers/">Papers</a>, <a href="{{ base_path }}/about-me/">more about me</a>, <a href="{{ base_path }}/list-100/">List 100</a>, or the <a href="{{ base_path }}/cv/">CV</a>.</p>
</div>


