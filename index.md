---
layout: default
title: Francis Visoiu Mistrih
---

# Welcome
I am Francis Visoiu Mistrih, a developer studying in Paris.

Currently a student at EPITA, I love learning new stuff about computer science, from low-level stuff to iPhone apps and web.

## About
Here is [my resume](http://cv.francisvm.com/).

Be sure to check more about me [here](/about/).

Don't hesitate to look around my [GitHub](https://github.com/thegameg) and [Bitbucket](http://bitbucket.org/thegameg) account.

Maybe it's even worth it to check my [Linkedin profile](https://www.linkedin.com/in/francisvm).

## Projects

<ul class="posts">
  {% for post in site.posts %}
    <li><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
