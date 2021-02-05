---
layout: post
title: "New seminar series / graduate course"
date: 2021-02-04 14:11
categories: [tutorial]
---

# How does the documentation in the ELN work? 


<hr>

<div class="post-categories">
  {% if post %}
    {% assign categories = post.categories %}
  {% else %}
    {% assign categories = page.categories %}
  {% endif %}
  {% for category in categories %}
  <a href="{{site.baseurl}}/categories/#{{category|slugize}}">{{category}}</a>
  {% unless forloop.last %}&nbsp;{% endunless %}
  {% endfor %}
</div>
