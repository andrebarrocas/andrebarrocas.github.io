---
title: Photography
permalink: /photography/
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
    {
      src: "{{ image.path | relative_url }}",
      alt: "{{ image.basename | remove: image.extname | replace: '-', ' ' | replace: '_', ' ' | capitalize }}",
      title: "{{ image.basename | remove: image.extname | replace: '-', ' ' | replace: '_', ' ' | capitalize }}"
    }{% unless forloop.last %},{% endunless %}
        {% endunless %}
      {% endif %}
    {% endfor %}
  ];

  // Create Pinterest-style masonry layout
  const gallery = document.getElementById('photography-gallery');
  gallery.innerHTML = '';
  gallery.style.display = 'block';

  // Create columns for masonry effect
  const numColumns = 4;
  const columns = [];
  for (let i = 0; i < numColumns; i++) {
    const column = document.createElement('div');
    column.className = 'col-lg-3 col-md-6 mb-4';
    column.style.breakInside = 'avoid';
    columns.push(column);
    gallery.appendChild(column);
  }

  // Distribute images across columns
  photographyImages.forEach((image, index) => {
    const columnIndex = index % numColumns;
    const imageElement = document.createElement('div');
    imageElement.className = 'card h-100 shadow-sm';
    imageElement.innerHTML = `
      <div class="card-img-container" style="position: relative; overflow: hidden;">
        <img src="${image.src}" 
             class="card-img-top" 
             alt="${image.alt}" 
             style="width: 100%; height: auto; transition: transform 0.3s ease; cursor: pointer;"
             data-zoom-src="${image.src}"
             onmouseover="this.style.transform='scale(1.05)'"
             onmouseout="this.style.transform='scale(1)'"
             onclick="window.open('${image.src}', '_blank')">
      </div>
      <div class="card-body p-3">
        <h6 class="card-title text-muted small mb-0">${image.title}</h6>
      </div>
    `;
    columns[columnIndex].appendChild(imageElement);
  });
});
</script>

<style>
#photography-gallery .card {
  border: none;
  border-radius: 12px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

#photography-gallery .card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 25px rgba(0,0,0,0.15) !important;
}

#photography-gallery .card-img-container {
  border-radius: 12px 12px 0 0;
  overflow: hidden;
}

#photography-gallery .card-img-top {
  border-radius: 0;
}

@media (max-width: 768px) {
  #photography-gallery .col-lg-3 {
    margin-bottom: 1rem;
  }
}
</style>
