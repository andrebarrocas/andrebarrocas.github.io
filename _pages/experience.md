---
layout: page
title: experience
permalink: /experience/
description: A growing collection my current and old experience.
nav: true
horizontal: false
---

<!-- pages/projects.md -->

<!-- Display projects without categories -->
  {%- assign experience_sorted = site.experience | reverse -%}   
  {% for page in experience_sorted %}

<div class="post">
<header class="post-header">
    <h1 class="post-title-experience">{{ page.title }}</h1>
    <p class="post-meta">{{ page.date | date: "%B %-d, %Y" }}{%- if page.author -%} • {{ page.author }}{%- endif -%}{%- if page.meta -%} • {{ page.meta }}{%- endif -%}</p>
    
    <article class="post-content">
    {{ page.content | emojify }}
    </article>


</header>
<h2 style="border-bottom: 1px solid var(--global-divider-color); margin-bottom: 1rem;"> </h2>

    {%- endfor %}
  
