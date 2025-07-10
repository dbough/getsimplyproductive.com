---
layout: default
title: Learn
description: "How-to articles and practical guides for small business productivity."
permalink: /learn
---

<!-- Learn Hero -->
<section class="learn-hero">
  <div class="container">
    <h1>Learn</h1>
    <p class="learn-subtitle">How-to articles and practical guides to help your small business work smarter.</p>
  </div>
</section>

{% if site.posts.size > 0 %}
<!-- Article List -->
<section class="article-list">
  <div class="container">
    <div class="posts-grid">
      {% for post in site.posts %}
        <article class="post-card">
          <div class="post-content">
            <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
            <div class="post-meta">
              <span class="post-date">{{ post.date | date: "%B %d, %Y" }}</span>
            </div>
            <p class="post-excerpt">{{ post.excerpt }}</p>
            <a href="{{ post.url }}" class="read-more">Read more →</a>
          </div>
        </article>
      {% endfor %}
    </div>
  </div>
</section>
{% else %}
<!-- Placeholder for future articles -->
<section class="coming-soon">
  <div class="container">
    <div class="coming-soon-content">
      <h3>🚀 Articles Coming Soon!</h3>
      <p>We're building a library of step-by-step how-to articles and practical guides for small business productivity. Check back soon for new content!</p>
      <ul>
        <li>How to automate repetitive tasks</li>
        <li>Tips for organizing your digital workspace</li>
        <li>Getting started with productivity tools</li>
        <li>And much more...</li>
      </ul>
      <p>If you have a topic you'd like to see, <a href="/contact">let us know</a>!</p>
    </div>
  </div>
</section>
{% endif %}
