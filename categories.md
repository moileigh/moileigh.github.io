---
layout: page
permalink: /categories/
title: Categories
---


<div>
{% for category in site.categories %}
  <div class="archive-group" style="position:relative;">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    
    <h3 class="category-head">{{ category_name }}</h3>
    <a name="{{ category_name | slugize }}" style="position:absolute; top: -5px;"></a>
    {% for post in site.categories[category_name] %}
    <article class="archive-item">
      <h4><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></h4>
    </article>
    {% endfor %}
  </div>
{% endfor %}
</div>
