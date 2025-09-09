---
layout: default
title: "Logs"
permalink: /logs/
---

<div class="max-w-prose stack">
  <h1>Logs</h1>
  <div class="list">
    {% assign sorted_logs = site.logs | sort: 'log_number' %}
    {% for log in sorted_logs %}
    <article class="journal">
      <div class="meta">[LOG {{ log.log_number | default: "##" }} | CHANNEL: {{ log.channel | default: "UNKNOWN" }}]</div>
      <p class="preview">
        {{ log.excerpt | strip_html | truncate: 200 }}
      </p>
      <a class="readmore button" href="{{ log.url | relative_url }}">Read More →</a>
    </article>
    {% endfor %}
  </div>
</div>

<style>
  /* Local-only helpers for preview truncation */
  .preview {
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
  }
  .readmore {
    display: inline-block;
    margin-top: 0.5rem;
  }
  .list > article + article {
    margin-top: 1rem;
  }
</style>
