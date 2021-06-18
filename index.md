---
layout: default
---

<h1>Recent Posts</h1>

<ul>
  {% for post in site.posts limit:3 %}
    <li>
      <h2><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h2>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>



This is now a blank page.

[With a link to the MD reference](./reference.html).

