---
layout: post-nav
title: All Posts
permalink: /posts/all/
---


<div>
{% for post in site.posts %}
  {% assign currentdate = post.date | date: "%Y" %}
    {% if currentdate != date %}
      <h3 id="{{post.date | date: "%Y"}}">{{ currentdate }}</h3>
      {% assign date = currentdate %}
    {% endif %}
    {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%} 
    <span class="post-meta">{{ post.date | date: date_format }}</span>
      <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
         {{ post.title | escape }}
        </a>  
      </h3> 
{% endfor %}
</div>




