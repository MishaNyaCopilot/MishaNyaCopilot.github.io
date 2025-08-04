---
layout: default
title: Home
---

<section class="hero">
  <h1>{{ site.title }}</h1>
  <p>{{ site.description }}</p>
  <div class="cta">
    <a class="button" href="{{ '/projects/' | relative_url }}">View Projects</a>
    <a class="button secondary" href="{{ '/about/' | relative_url }}">About Me</a>
  </div>
</section>

<section>
  <h2>Featured Projects</h2>
  <div class="grid">
    {%- assign featured = site.projects | where: "featured", true -%}
    {%- for project in featured limit:6 -%}
      <a class="card" href="{{ project.url | relative_url }}">
        {%- if project.cover -%}
        <img src="{{ project.cover | relative_url }}" alt="{{ project.title }} cover" loading="lazy" />
        {%- endif -%}
        <div class="card-content">
          <h3>{{ project.title }}</h3>
          <p>{{ project.excerpt | default: project.subtitle }}</p>
          <div class="meta">
            <span>{{ project.tech | join: ', ' }}</span>
            <span>{{ project.date | date: "%b %Y" }}</span>
          </div>
        </div>
      </a>
    {%- endfor -%}
    {%- if featured.size == 0 -%}
      <p>No featured projects yet. Mark a project with <code>featured: true</code>.</p>
    {%- endif -%}
  </div>
</section>