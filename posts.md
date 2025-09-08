---
layout: default
title: "Archive"
permalink: /posts/
---

<div class="max-w-prose stack">
  <h1>Archive</h1>
  <p class="dim">Digital fragments and system logs from the network.</p>
  
  <div class="list">
    {% for post in site.posts %}
    <article class="journal">
      <div class="meta">[{{ post.date | date: "%Y.%m.%d" }} | {{ post.author | default: "TRACE" }}]</div>
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      <p class="preview">
        {{ post.excerpt | strip_html | truncate: 200 }}
      </p>
      {% if post.tags.size > 0 %}
      <div class="tags">
        {% for tag in post.tags %}
          <span class="badge">{{ tag }}</span>
        {% endfor %}
      </div>
      {% endif %}
    </article>
    {% endfor %}
  </div>
</div>

<style>
  .list > article + article {
    margin-top: 2rem;
  }
  .tags {
    margin-top: 1rem;
  }
  .tags .badge {
    margin-right: 0.5rem;
  }
</style>
