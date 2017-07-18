---
title: Welcome!
---

# :wave: Welcome!

This corner of the internet holds some of my written thoughts. Topics may include God, programming, dancing, relationships, reading, movies, nature, New Zealand, and anything else that happens to cross my mind. Nau mai haere mai ki a koutou. Enjoy!

## Tags

<p class="all-tags">
  {% for tag in site.tags %}
    <a href="/{{ tag | first | slugize }}/" style="font-size: {{ tag | last | size | times: 100 | divided_by: site.tags.size | plus: 70 }}%">
            {{ tag | first }}
    </a>
  {% endfor %}
</p>

## All posts

<ul class="all-posts">
  {% for post in site.posts %}
    <li>
      {{ post.date | date: "%Y-%m-%d" }} <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
