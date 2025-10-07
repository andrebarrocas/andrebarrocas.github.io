---
layout: default
title: Illustration
permalink: /illustration/
---

<div class="row">
  <div class="col-lg-12">
    <h1 class="mb-4">Illustration</h1>
    <p class="mb-5">Digital artwork and visual explorations.</p>
  </div>
</div>

<div class="row">
  <div class="col-lg-3 col-md-6 mb-3">
    {% assign ill_index = 0 %}
    {% for image in site.static_files %}
      {% if image.path contains 'assets/img/illustration/' and (image.extname == '.jpg' or image.extname == '.webp') %}
        {% unless image.basename contains 'DS_Store' %}
          {% assign remainder = ill_index | modulo: 4 %}
          {% if remainder == 0 %}
            <div class="mb-3">
              <img src="{{ image.path | relative_url }}" 
                   class="img-fluid rounded shadow-sm" 
                   alt="Illustration" 
                   style="width: 100%; height: auto; transition: transform 0.3s ease, box-shadow 0.3s ease; cursor: pointer;"
                   onmouseover="this.style.transform='scale(1.02)'; this.style.boxShadow='0 8px 25px rgba(0,0,0,0.15)'"
                   onmouseout="this.style.transform='scale(1)'; this.style.boxShadow='0 2px 10px rgba(0,0,0,0.1)'"
                   onclick="window.open('{{ image.path | relative_url }}', '_blank')">
            </div>
          {% endif %}
          {% assign ill_index = ill_index | plus: 1 %}
        {% endunless %}
      {% endif %}
    {% endfor %}
  </div>
  <div class="col-lg-3 col-md-6 mb-3">
    {% assign ill_index = 0 %}
    {% for image in site.static_files %}
      {% if image.path contains 'assets/img/illustration/' and (image.extname == '.jpg' or image.extname == '.webp') %}
        {% unless image.basename contains 'DS_Store' %}
          {% assign remainder = ill_index | modulo: 4 %}
          {% if remainder == 1 %}
            <div class="mb-3">
              <img src="{{ image.path | relative_url }}" 
                   class="img-fluid rounded shadow-sm" 
                   alt="Illustration" 
                   style="width: 100%; height: auto; transition: transform 0.3s ease, box-shadow 0.3s ease; cursor: pointer;"
                   onmouseover="this.style.transform='scale(1.02)'; this.style.boxShadow='0 8px 25px rgba(0,0,0,0.15)'"
                   onmouseout="this.style.transform='scale(1)'; this.style.boxShadow='0 2px 10px rgba(0,0,0,0.1)'"
                   onclick="window.open('{{ image.path | relative_url }}', '_blank')">
            </div>
          {% endif %}
          {% assign ill_index = ill_index | plus: 1 %}
        {% endunless %}
      {% endif %}
    {% endfor %}
  </div>
  <div class="col-lg-3 col-md-6 mb-3">
    {% assign ill_index = 0 %}
    {% for image in site.static_files %}
      {% if image.path contains 'assets/img/illustration/' and (image.extname == '.jpg' or image.extname == '.webp') %}
        {% unless image.basename contains 'DS_Store' %}
          {% assign remainder = ill_index | modulo: 4 %}
          {% if remainder == 2 %}
            <div class="mb-3">
              <img src="{{ image.path | relative_url }}" 
                   class="img-fluid rounded shadow-sm" 
                   alt="Illustration" 
                   style="width: 100%; height: auto; transition: transform 0.3s ease, box-shadow 0.3s ease; cursor: pointer;"
                   onmouseover="this.style.transform='scale(1.02)'; this.style.boxShadow='0 8px 25px rgba(0,0,0,0.15)'"
                   onmouseout="this.style.transform='scale(1)'; this.style.boxShadow='0 2px 10px rgba(0,0,0,0.1)'"
                   onclick="window.open('{{ image.path | relative_url }}', '_blank')">
            </div>
          {% endif %}
          {% assign ill_index = ill_index | plus: 1 %}
        {% endunless %}
      {% endif %}
    {% endfor %}
  </div>
  <div class="col-lg-3 col-md-6 mb-3">
    {% assign ill_index = 0 %}
    {% for image in site.static_files %}
      {% if image.path contains 'assets/img/illustration/' and (image.extname == '.jpg' or image.extname == '.webp') %}
        {% unless image.basename contains 'DS_Store' %}
          {% assign remainder = ill_index | modulo: 4 %}
          {% if remainder == 3 %}
            <div class="mb-3">
              <img src="{{ image.path | relative_url }}" 
                   class="img-fluid rounded shadow-sm" 
                   alt="Illustration" 
                   style="width: 100%; height: auto; transition: transform 0.3s ease, box-shadow 0.3s ease; cursor: pointer;"
                   onmouseover="this.style.transform='scale(1.02)'; this.style.boxShadow='0 8px 25px rgba(0,0,0,0.15)'"
                   onmouseout="this.style.transform='scale(1)'; this.style.boxShadow='0 2px 10px rgba(0,0,0,0.1)'"
                   onclick="window.open('{{ image.path | relative_url }}', '_blank')">
            </div>
          {% endif %}
          {% assign ill_index = ill_index | plus: 1 %}
        {% endunless %}
      {% endif %}
    {% endfor %}
  </div>
</div>

<style>
.row img {
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.row img:hover {
  transform: scale(1.02);
  box-shadow: 0 8px 25px rgba(0,0,0,0.15);
}

@media (max-width: 768px) {
  .col-lg-3 {
    margin-bottom: 1rem;
  }
}
</style>
