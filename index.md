---
layout: default
title: Work
---

<section class="hero wrap">
  <div class="hero-grid">
    <div class="hero-text">
      <h1 class="display">{{ site.author }}</h1>
      <p class="lede">
        Currently finishing my MSc in Artificial Intelligence at Imperial College
        London. As part of my dissertation, I am using Generative AI for climate modelling. 
        Before Imperial, I spent a short while at a robotic-harvesting startup
        building computer-vision pipelines. I also worked for four years at
        Société Générale's Global Markets team trading equity derivatives with hedge funds. 
        Earlier, I read Mathematics &amp; Economics at the LSE, graduating with a First.
        
        My current focus is on AI that reaches the places it is most needed. 
        That has meant sound anomaly fault detection for machines running on 
        a chip with only 256KB of memory, generative models reconstructing past climate, 
        and most recently writing on whether the EU AI Act’s rules for marking AI-edited 
        images can be made precise enough to enforce.
      </p>
      <ul class="inline-links">
        <li><a href="https://github.com/{{ site.github_username }}">GitHub</a></li>
        <li><a href="{{ site.linkedin_url }}">LinkedIn</a></li>
        <li><a href="{{ '/cv/' | relative_url }}">CV</a></li>
      </ul>
    </div>
    <img class="portrait" src="{{ '/assets/img/evgeni-georgiev.jpg' | relative_url }}"
         alt="Portrait of {{ site.author }}" width="640" height="640">
  </div>
</section>

<section class="wrap section">
  <div class="spread">
    <h2 class="label">Projects</h2>
    <div>
      {%- for p in site.data.projects %}
      <article class="repo">
        <p class="repo-path">{{ site.github_username }} / <b>{{ p.name }}</b></p>
        <h3>{{ p.title }}</h3>
        <p>{{ p.blurb }}</p>
        {%- if p.tags %}
        <ul class="tags">{% for t in p.tags %}<li>{{ t }}</li>{% endfor %}</ul>
        {%- endif %}
        <p class="repo-links">
          <a href="{{ p.repo }}">Source on GitHub</a>
          {%- if p.link and p.link != "" %}<a href="{{ p.link }}">{{ p.link_label | default: "More" }}</a>{% endif %}
        </p>
      </article>
      {%- endfor %}
    </div>
  </div>
</section>

<section class="wrap section">
  <div class="spread">
    <h2 class="label">Writing</h2>
    <div>
      <ul class="post-list">
        {%- for post in site.posts limit: 3 %}
        <li>
          <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%d %b %Y" }}</time>
          <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          {%- if post.standfirst %}<span class="post-blurb">{{ post.standfirst }}</span>{% endif %}
        </li>
        {%- endfor %}
      </ul>
      <p class="fine"><a href="{{ '/blog/' | relative_url }}">All writing &rarr;</a></p>
    </div>
  </div>
</section>
