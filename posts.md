---
layout: all-posts
title: Posts
permalink: /posts/
---


{%- if site.posts.size > 0 -%} 
<ul class="post-list">
  {%- for post in site.posts limit:25-%} 
  {% assign currentdate = post.date | date: "%Y" %}
   {% if currentdate != date %}
  <div >
  <h2 class="year-marker" id="{{post.date | date: "%Y"}}" >{{ currentdate }}</h2>
  <a href="#top" class="to-top">return to top</a>
  </div>
      {% assign date = currentdate %}
   {% endif %}
  <li>
  <h3>
    <a class="post-link" href="{{ post.url | relative_url }}">
     {{ post.title | escape }}
    </a>  
    {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%} 
    <span class="post-meta">{{ post.date | date: date_format }}</span>
  </h3> 
  </li>
  {%- endfor -%}
</ul> 
{%- endif -%}

<div class="more-posts"><a href="all">see all posts</a></div>



