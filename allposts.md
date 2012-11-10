---
layout: default
---
### List of all posts by date

<div class="link">
  <ul class="recent">
  {% for post in site.posts %}
    <li>{{ post.date | date_to_string }} <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
  </ul>
</div>

[Back to start](index.html)
