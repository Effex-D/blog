---
layout: default
---

<h1>Recent Posts</h1>

Or browse all of the entries [here](./posts).

<ul>
  {% for post in site.posts limit:4 %}
    <li>
      <h2><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h2>
      {{ post }}
    </li>
  {% endfor %}
</ul>


