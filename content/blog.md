---
title: Blog
description: Update form Blogs
pagination:
  data: collections.posts
  size: 5
  reverse: true
testdata:
 - item1
 - item2
 - item3
 - item4
permalink: "blog/{% if pagination.pageNumber > 0 %}page-{{ pagination.pageNumber + 1 }}/{% endif %}index.html"
---
{%- for item in pagination.items %}
<div class="col-md-10 mx-auto p-3 p-md-5 border-bottom">
<h3 class="text-big"><strong><a href="{{item.url}}">{{item.data.title}}</a></strong></h3>
{% if page.date %}<p><time datetime="{{ item.date | htmlDateString }}"><code class="text-dark"><small>{{ item.date | readableDate("LLLL yyyy") }}</small></code></time></p>{% endif %}
<p>{{ item.data.description }}</p>
</div>{% endfor -%} 
<div class="container">
<div class="row border-top">
<div class="col-6 p-3 text-pag">{% if pagination.href.previous %}<a class="header-title ms-3" href="{{ pagination.href.previous }}">← Prev</a>{% endif %}</div>
<div class="col-6 p-3 text-end text-pag">{% if pagination.href.next %}<a class="header-title me-3" href="{{ pagination.href.next }}">Next →</a>{% endif %}</div>
</div>
</div>
