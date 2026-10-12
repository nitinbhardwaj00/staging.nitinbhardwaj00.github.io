---
permalink: /blog/
title: "Blog"
layout: single
author_profile: true
classes: wide
excerpt: "Notes on AI, finance and data — written by someone who has to make the numbers add up on Monday morning."
---

<style>
  .nb-hero { padding: 1.5em 0 1em; border-bottom: 1px solid #e6e6e6; margin-bottom: 1.5em; }
  .nb-hero h2 { margin: 0 0 .3em; font-size: 1.6em; line-height: 1.25; border: 0; }
  .nb-hero p { color: #555; margin: 0; max-width: 46em; }
  .nb-pillars { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 1em; margin: 1.5em 0 2em; }
  .nb-pillar { border: 1px solid #e6e6e6; border-radius: 8px; padding: 1em 1.1em; background: #fafafa; }
  .nb-pillar h3 { margin: 0 0 .35em; font-size: 1em; text-transform: uppercase; letter-spacing: .06em; }
  .nb-pillar p { margin: 0; font-size: .85em; color: #555; }
  .nb-pillar.finance h3 { color: #1f6f5c; }
  .nb-pillar.data h3 { color: #2a5d9f; }
  .nb-pillar.ai h3 { color: #8a4baf; }
  .nb-featured { border-left: 4px solid #2a5d9f; padding: .6em 0 .6em 1.1em; margin: 0 0 2em; }
  .nb-featured .nb-kicker { font-size: .7em; text-transform: uppercase; letter-spacing: .1em; color: #888; }
  .nb-featured h3 { margin: .2em 0 .4em; font-size: 1.3em; }
  .nb-featured h3 a { text-decoration: none; }
  .nb-featured p { margin: 0; color: #444; }
  .nb-list { list-style: none; margin: 0; padding: 0; }
  .nb-post { padding: 1em 0; border-top: 1px solid #eee; }
  .nb-post:first-child { border-top: 0; }
  .nb-post h3 { margin: 0 0 .25em; font-size: 1.1em; }
  .nb-post h3 a { text-decoration: none; }
  .nb-meta { font-size: .75em; color: #888; margin-bottom: .4em; }
  .nb-post p { margin: 0 0 .4em; font-size: .9em; color: #444; }
  .nb-tag { display: inline-block; font-size: .7em; padding: .1em .55em; margin: 0 .3em .3em 0; border-radius: 999px; background: #eef2f7; color: #2a5d9f; text-decoration: none; }
  .nb-subscribe { margin-top: 2.5em; padding: 1.2em; border-radius: 8px; background: #f3f6f9; font-size: .9em; }
  @media (prefers-color-scheme: dark) {
    .nb-pillar { background: transparent; }
  }
</style>

<div class="nb-hero">
  <h2>Where finance, data and AI meet the real P&amp;L.</h2>
  <p>I've spent about ten years in Germany building analytics functions, running FP&amp;A, implementing EPM tools and working on the investment side. This blog is where I write down what actually worked, what didn't, and what I'd do differently — with a bias for opinions you can argue with.</p>
</div>

<div class="nb-pillars">
  <div class="nb-pillar finance">
    <h3>Finance</h3>
    <p>FP&amp;A, SaaS metrics, EPM platforms, planning that survives contact with the board.</p>
  </div>
  <div class="nb-pillar data">
    <h3>Data</h3>
    <p>Metric governance, semantic layers, dbt, and building analytics teams from zero.</p>
  </div>
  <div class="nb-pillar ai">
    <h3>AI</h3>
    <p>Where LLMs help finance teams today, where they quietly break things, and how to tell.</p>
  </div>
</div>

{% assign featured = site.posts | where: "featured", true | first %}
{% if featured %}
<div class="nb-featured">
  <div class="nb-kicker">Start here</div>
  <h3><a href="{{ featured.url | relative_url }}">{{ featured.title }}</a></h3>
  <p>{{ featured.excerpt | strip_html | truncate: 260 }}</p>
</div>
{% endif %}

## All posts

<ul class="nb-list">
{% for post in site.posts %}
  {% unless post.featured %}
  <li class="nb-post">
    <div class="nb-meta">{{ post.date | date: "%d %b %Y" }}{% if post.read_time %} · {% include read-time.html %}{% endif %}</div>
    <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    <p>{{ post.excerpt | strip_html | truncate: 220 }}</p>
    {% for tag in post.tags %}<a class="nb-tag" href="{{ '/tags/' | relative_url }}#{{ tag | slugify }}">{{ tag }}</a>{% endfor %}
  </li>
  {% endunless %}
{% endfor %}
</ul>

<div class="nb-subscribe">
  <strong>Want the next one?</strong> Follow along via the <a href="{{ '/feed.xml' | relative_url }}">RSS feed</a>, or reach out on <a href="https://www.linkedin.com/in/YOUR-LINKEDIN/">LinkedIn</a> — I read every message, especially the ones that disagree.
</div>
