---
layout: all-posts
permalink: /posts/category/
title: Posts By Category
---


<div>
{% for category in site.categories %}
  <div class="archive-group" style="position:relative;">
    {% capture category_name %}{{ category | first }}{% endcapture %}
   
   <h2 class="category-head">{{ category_name }}</h2>
   <a name="{{ category_name | slugize }}" style="position:absolute; top: -5px;"></a>
   <ul class="post-list">
    {% for post in site.categories[category_name] %}
   <li>
   <h4>
     <a class="post-link" href="{{ post.url | relative_url }}">
       {{ post.title | escape }}
     </a>  
     {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%} 
     <span class="post-meta">{{ post.date | date: date_format }}</span>
   </h4> 
   </li> 
  {% endfor %}
   </ul> 
  </div>
{% endfor %}
</div>
