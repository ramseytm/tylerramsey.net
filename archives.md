---
layout: page
title: Archives
page-title: Past Posts
permalink: /archives/
---

<div id="archive">
  <h3>{{ site.posts.first.date | date: '%Y' }}</h3>
  {%for post in site.posts %}
    {% unless post.next %}
      <ul class="past-posts ">
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        </ul>
        <h3>{{ post.date | date: '%Y' }}</h3>
        <ul class="past-posts">
      {% endif %}
    {% endunless %}
      <li><time>{{ post.date | date:"%d %b" }}</time> -> <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
  </ul>
</div>
