---
layout: home
title: Home
---

<div class="page">
  <h1 class="page-title">{{ Hello }}</h1>

<hr/>

I'll post things from my research here every now and then

:coffee:


<hr>
<dl>
  {% for post in site.posts %}
    <p class="message">
    <span class="post-title">{{ post.title }}</span>
    <span class="post-date">{{ post.date | date_to_string }}</span>
    {% if post.thumbnail %}
      <img src="/img/{{ post.thumbnail }}" />
    {% elsif post.thumbnail_link %}
      <img src = "{{ post.thumbnail_link }}" />
    {% endif %}
    {% if post.abstract %}
    {{ post.abstract }}
    {% endif %}
    <br> <a href="{{ post.url }}">{{ "read more" }}</a>
  </p>
  {% endfor %}
</dl>


</div>
