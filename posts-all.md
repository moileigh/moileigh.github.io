---
layout: all-posts
title: All Posts
permalink: /posts/all/
---


<ul class="post-list">
{% for post in site.posts %}
  {% assign currentdate = post.date | date: "%Y" %}
   {% if currentdate != date %}
      <h1 id="{{post.date | date: "%Y"}}">{{ currentdate }}</h1>
      {% assign date = currentdate %}
   {% endif %}
  <li>
   <h2>
    <a class="post-link" href="{{ post.url | relative_url }}">
     {{ post.title | escape }}
    </a>  
     {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%} 
     <span class="post-meta">{{ post.date | date: date_format }}</span>
   </h2> 
  </li>
{% endfor %}
</ul>


