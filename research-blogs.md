---
layout: page
title: "Research Blogs"
subtitle: "Research writing from the lab"
---

<div class="blog-grid">
  {% if site.data.blogs.size > 0 %}
    {% for blog in site.data.blogs %}
      <article class="blog-card">
        {% if blog.image %}
          {% assign image_src = blog.image %}
          {% unless image_src contains '://' %}
            {% assign image_first_char = image_src | slice: 0 %}
            {% if image_first_char == '/' %}
              {% assign image_src = site.baseurl | append: image_src %}
            {% else %}
              {% assign image_src = site.baseurl | append: '/' | append: image_src %}
            {% endif %}
          {% endunless %}
          {% if blog.url %}
            <a class="blog-card-image-link" href="{{ blog.url }}" target="_blank" rel="noopener noreferrer">
              <img class="blog-card-image" src="{{ image_src }}" alt="{{ blog.title }}">
            </a>
          {% else %}
            <img class="blog-card-image" src="{{ image_src }}" alt="{{ blog.title }}">
          {% endif %}
        {% endif %}

        <div class="blog-card-body">
          <h2 class="blog-card-title">
            {% if blog.url %}
              <a href="{{ blog.url }}" target="_blank" rel="noopener noreferrer">{{ blog.title }}</a>
            {% else %}
              {{ blog.title }}
            {% endif %}
          </h2>

          {% if blog.authors %}
            <div class="blog-card-authors">{{ blog.authors }}</div>
          {% endif %}

          {% if blog.byline %}
            <p class="blog-card-byline">{{ blog.byline }}</p>
          {% endif %}
        </div>
      </article>
    {% endfor %}
  {% else %}
    <p class="text-muted">Research blog posts will be listed here.</p>
  {% endif %}
</div>
