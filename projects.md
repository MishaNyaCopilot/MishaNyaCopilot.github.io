---
layout: default
title: Projects
permalink: /projects/
---

<h1>Projects</h1>
<div class="grid">
  {%- assign items = site.projects | sort: "date" | reverse -%}
  {%- for project in items -%}
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
</div>