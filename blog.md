---
layout: default
title: Blog
description: "Practical productivity tips, insights, and strategies for small businesses. Learn how to work smarter, not harder."
---

<!-- Blog Hero -->
<section class="blog-hero">
  <h1>{{ page.title | default: "Productivity Insights" }}</h1>
  <p class="blog-subtitle">{{ page.description | default: "Practical tips and strategies to help your small business work smarter, not harder." }}</p>
</section>

<!-- Featured Post -->
{% assign featured_post = site.posts | where: "featured", true | first %}
{% if featured_post %}
<section class="featured-post">
  <h2>Featured Article</h2>
  <article class="post-card featured">
    <div class="post-image">
      {% if featured_post.image %}
        <img src="{{ featured_post.image }}" alt="{{ featured_post.title }}">
      {% else %}
        <div class="post-image-placeholder">📚</div>
      {% endif %}
    </div>
    <div class="post-content">
      <h3><a href="{{ featured_post.url }}">{{ featured_post.title }}</a></h3>
      <div class="post-meta">
        <time datetime="{{ featured_post.date | date_to_xmlschema }}">
          {{ featured_post.date | date: "%B %d, %Y" }}
        </time>
        {% if featured_post.categories.size > 0 %}
          <span class="post-category">{{ featured_post.categories.first }}</span>
        {% endif %}
      </div>
      <p class="post-excerpt">{{ featured_post.excerpt | strip_html | truncatewords: 30 }}</p>
      <a href="{{ featured_post.url }}" class="read-more">Read More &rarr;</a>
    </div>
  </article>
</section>
{% endif %}

<!-- Recent Posts -->
<section class="recent-posts">
  <h2>Recent Articles</h2>
  {% if site.posts.size > 0 %}
    <div class="posts-grid">
      {% for post in site.posts limit: 6 %}
        {% unless post.featured %}
          <article class="post-card">
            <div class="post-image">
              {% if post.image %}
                <img src="{{ post.image }}" alt="{{ post.title }}">
              {% else %}
                <div class="post-image-placeholder">📄</div>
              {% endif %}
            </div>
            <div class="post-content">
              <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
              <div class="post-meta">
                <time datetime="{{ post.date | date_to_xmlschema }}">
                  {{ post.date | date: "%B %d, %Y" }}
                </time>
                {% if post.categories.size > 0 %}
                  <span class="post-category">{{ post.categories.first }}</span>
                {% endif %}
              </div>
              <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 20 }}</p>
              <a href="{{ post.url }}" class="read-more">Read More &rarr;</a>
            </div>
          </article>
        {% endunless %}
      {% endfor %}
    </div>
  {% else %}
    <div class="coming-soon">
      <div class="coming-soon-content">
        <h3>🚀 Coming Soon!</h3>
        <p>We're preparing valuable productivity insights and practical tips to help your small business thrive. Our blog will feature:</p>
        <ul>
          <li>Weekly productivity tips and strategies</li>
          <li>Tool reviews and recommendations</li>
          <li>Small business success stories</li>
          <li>Behind-the-scenes insights</li>
          <li>Expert interviews and guest posts</li>
        </ul>
        <p>Stay tuned for our first posts coming soon!</p>
        <div class="button-container">
          <a href="/contact" class="button-link primary">Get Notified When We Launch</a>
          <a href="/products" class="button-link secondary">Explore Our Solutions</a>
        </div>
      </div>
    </div>
  {% endif %}
</section>

<!-- Categories -->
{% if site.categories.size > 0 %}
<section class="blog-categories">
  <h2>Categories</h2>
  <div class="categories-grid">
    {% for category in site.categories %}
      <a href="/blog/category/{{ category[0] | slugify }}/" class="category-card">
        <h4>{{ category[0] }}</h4>
        <span class="post-count">{{ category[1] | size }} articles</span>
      </a>
    {% endfor %}
  </div>
</section>
{% endif %}

<!-- Newsletter Signup -->
<section class="blog-newsletter">
  <div class="newsletter-content">
    <h2>Stay Updated</h2>
    <p>Get weekly productivity tips and insights delivered straight to your inbox.</p>
    <div class="button-container">
      <a href="/contact" class="button-link primary">Subscribe to Newsletter</a>
    </div>
  </div>
</section>
