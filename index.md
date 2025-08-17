---
layout: default
title: ホーム
permalink: /
---

<section class="hero" style="margin-bottom: 2rem; text-align: center;">
  <h2>{{ site.description }}</h2>
  <p>最新の記事をお届けします。</p>
</section>

<div class="post-list">
{% assign posts = site.posts | sort: 'date' | reverse %}
{% for post in posts %}
  <article class="post-card">
    {% if post.image %}
    <a href="{{ post.url | relative_url }}"><img src="{{ post.image | relative_url }}" alt="{{ post.title }}"></a>
    {% endif %}
    <div class="post-card-content">
      <h2 class="post-card-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p class="post-card-meta">{{ post.date | date: '%Y年%-m月%-d日' }}{% if post.author %} · {{ post.author }}{% endif %}</p>
      <p class="post-card-excerpt">{{ post.excerpt | strip_html | truncate: 120 }}</p>
      <a class="read-more" href="{{ post.url | relative_url }}">続きを読む</a>
    </div>
  </article>
{% endfor %}
</div>