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

{% assign learning_posts = "" | split: "" %}
{% for post in site.posts %}
  {% if post.categories contains "learning-notes" %}
    {% assign learning_posts = learning_posts | push: post %}
  {% endif %}
{% endfor %}

{% if learning_posts.size > 0 %}
  {% assign sorted_posts = learning_posts | sort: "date" | reverse %}
  <ul>
    {% for post in sorted_posts %}
      <li>
        <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      </li>
    {% endfor %}
  </ul>
{% else %}
  <div class="no-notes">
    <p>No learning notes yet. Check back soon!</p>
  </div>
{% endif %}