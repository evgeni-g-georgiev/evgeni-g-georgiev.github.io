---
layout: default
title: Writing
permalink: /blog/
---

<section class="wrap section">
  <header class="page-head spread">
    <p class="label">Writing</p>
    <div>
      <h1>Notes and essays</h1>
      
    </div>
  </header>

  <div class="spread">
    <p class="label"></p>
    <div>
      <ul class="post-list">
        {%- for post in site.posts %}
        <li>
          <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%d %b %Y" }}</time>
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          {%- if post.standfirst %}<span class="post-blurb">{{ post.standfirst }}</span>{% endif %}
        </li>
        {%- endfor %}
      </ul>
    </div>
  </div>
</section>
