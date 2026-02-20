---
layout: archive
title: "Tech Articles"
permalink: /tech/
author_profile: true
---


Technical articles, tutorials and notes.

---

## Articles

{% assign tech_posts = site.posts | where_exp: "post", "post.categories contains 'ACM'" | sort: "date" | reverse %}

<ul class="article-list">
  {% for post in tech_posts %}
    <li class="article-item">
      <span class="article-date">{{ post.date | date: "%Y-%m-%d" }}</span>
      <a href="{{ post.url }}" class="article-title">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

<style>
.article-list {
  list-style: none;
  padding: 0;
  margin: 2rem 0;
}

.article-item {
  display: flex;
  align-items: center;
  padding: 0.8rem 0;
  border-bottom: 1px solid #eaeaea;
}

.article-item:hover {
  background-color: #f8f9fa;
}

.article-date {
  min-width: 100px;
  color: #666;
  font-size: 0.9rem;
  font-family: monospace;
}

.article-title {
  flex: 1;
  color: #2563eb;
  text-decoration: none;
  font-size: 1.1rem;
}

.article-title:hover {
  text-decoration: underline;
}

@media (max-width: 768px) {
  .article-item {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.3rem;
  }
  
  .article-date {
    min-width: auto;
  }
}
</style>