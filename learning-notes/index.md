---
layout: archive
title: "Learning Notes"
permalink: /learning-notes/
author_profile: true
---

# 📚 Learning Notes

Here are my technical learning notes and study summaries.

---

## 📝 Recent Notes

{% assign learning_posts = site.posts | where_exp: "post", "post.categories contains 'learning-notes'" %}
{% for post in learning_posts %}
  <article class="post-item">
    <h2 class="post-title">
      <a href="{{ post.url }}">{{ post.title }}</a>
    </h2>
    
    <div class="post-meta">
      <time datetime="{{ post.date | date_to_xmlschema }}">
        {{ post.date | date: "%B %d, %Y" }}
      </time>
      {% if post.tags.size > 0 %}
        <span class="post-tags">
          {% for tag in post.tags %}
            <a href="/tags/#{{ tag | slugify }}" class="tag">{{ tag }}</a>
          {% endfor %}
        </span>
      {% endif %}
    </div>
    
    {% if post.excerpt %}
      <div class="post-excerpt">
        {{ post.excerpt | markdownify | truncatewords: 50 }}
      </div>
    {% endif %}
    
    {% if post.difficulty %}
      <div class="difficulty">
        Difficulty: 
        {% for i in (1..5) %}
          {% if i <= post.difficulty %}
            ⭐
          {% else %}
            ☆
          {% endif %}
        {% endfor %}
        ({{ post.difficulty }}/5)
      </div>
    {% endif %}
    
    <hr class="post-divider">
  </article>
{% endfor %}