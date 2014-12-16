---
layout: page
title: Projects
permalink: /projects/
---

Most of my projects are available on my
[GitHub](https://github.com/thegameg) and
[Bitbucket](http://bitbucket.org/thegameg) accounts.

---

<div class="posts">
  {% for post in site.posts %}
    <div class="post">
      <a href="{{ post.url | prepend: site.baseurl }}" class="post-link">
        <h3 class="h3 post-title">{{ post.title }}</h3>
        <p class="post-summary">{{ post.summary }}</p>
      </a>
    </div>
  {% endfor %}
</div>
