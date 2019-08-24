---
layout: all-posts
title: Posts
permalink: /posts/
---


{%- if site.posts.size > 0 -%} 
<ul class="post-list">
  {%- for post in site.posts limit:25-%} 
  <li>
  <h2>
    <a class="post-link" href="{{ post.url | relative_url }}">
     {{ post.title | escape }}
    </a>  
    {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%} 
    <span class="post-meta">{{ post.date | date: date_format }}</span>
  </h2> 
  </li>
  {%- endfor -%}
</ul> 
{%- endif -%}

<h2><a href="all">See all posts</a></h2>



