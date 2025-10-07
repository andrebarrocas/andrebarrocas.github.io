---
layout: default
title: Photography
permalink: /photography/
nav: true
---

<div class="row">
  <div class="col-lg-12">
    <h1 class="mb-4">Photography</h1>
    <p class="mb-5">A collection of moments captured through my lens.</p>
  </div>
</div>

<div class="row" id="photography-gallery">
  <!-- Photography images will be loaded here -->
</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
  // Define the photography images
  const photographyImages = [
    {% for image in site.static_files %}
      {% if image.path contains 'assets/img/photos/' and image.extname == '.jpg' %}
        {% unless image.basename contains 'DS_Store' %}
    "{{ image.path | relative_url }}"{% unless forloop.last %},{% endunless %}
        {% endunless %}
      {% endif %}
    {% endfor %}
  ];

  // Create 3-column grid layout
  const gallery = document.getElementById('photography-gallery');
  gallery.innerHTML = '';
  gallery.style.display = 'block';

  // Create 3 columns
  const numColumns = 3;
  const columns = [];
  for (let i = 0; i < numColumns; i++) {
    const column = document.createElement('div');
    column.className = 'col-lg-4 col-md-6 mb-3';
    column.style.breakInside = 'avoid';
    columns.push(column);
    gallery.appendChild(column);
  }

  // Distribute images across columns
  photographyImages.forEach((imageSrc, index) => {
    const columnIndex = index % numColumns;
    const imageElement = document.createElement('div');
    imageElement.className = 'mb-3';
    imageElement.innerHTML = `
      <img src="${imageSrc}" 
           class="img-fluid rounded shadow-sm" 
           alt="Photography" 
           style="width: 100%; height: auto; transition: transform 0.3s ease, box-shadow 0.3s ease; cursor: pointer;"
           onmouseover="this.style.transform='scale(1.02)'; this.style.boxShadow='0 8px 25px rgba(0,0,0,0.15)'"
           onmouseout="this.style.transform='scale(1)'; this.style.boxShadow='0 2px 10px rgba(0,0,0,0.1)'"
           onclick="window.open('${imageSrc}', '_blank')">
    `;
    columns[columnIndex].appendChild(imageElement);
  });
});
</script>

<style>
#photography-gallery img {
  border-radius: 8px;
  box-shadow: 0 2px 10px rgba(0,0,0,0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

#photography-gallery img:hover {
  transform: scale(1.02);
  box-shadow: 0 8px 25px rgba(0,0,0,0.15);
}

@media (max-width: 768px) {
  #photography-gallery .col-lg-4 {
    margin-bottom: 1rem;
  }
}
</style>
