---
layout: default
---
### Development focus

[Look here for the site with real updates](http://atta-metta.net/about).

### List of all posts by date

<div class="link">
  <ul class="recent">
  {% for post in site.posts %}
    <li>{{ post.date | date_to_string }} <a href="{{ post.url }}">➯ {{ post.title }}</a> <a class="dsq_count" href="{{ post.url }}#disqus_thread"></a></li>
  {% endfor %}
  </ul>
</div>
