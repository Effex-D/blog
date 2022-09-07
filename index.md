---
layout: default
---

<h1>Recent Posts</h1>

Or browse all of the entries [here](/blog/posts).

<ul>
  {% for post in site.posts limit:10 %}
    <li>
      <h2><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h2>
      <time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date_to_long_string }}</time>
      {{ post.content }}
    </li>
  {% endfor %}
</ul>


