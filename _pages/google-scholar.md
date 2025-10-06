---
title: Google Scholar
permalink: /google-scholar/
nav: true
---

<div class="row">
  <div class="col-lg-12">
    <h1 class="mb-4">Google Scholar</h1>
    <p class="mb-5">Research publications and academic work.</p>
  </div>
</div>

<div class="row">
  <div class="col-lg-8 col-md-10 col-sm-12 mx-auto">
    <div class="card shadow-sm">
      <div class="card-body text-center py-5">
        <div class="mb-4">
          <i class="ai ai-google-scholar fa-3x text-muted"></i>
        </div>
        <h3 class="card-title mb-3">Academic Profile</h3>
        <p class="card-text text-muted mb-4">
          Visit my Google Scholar profile to explore my research publications, 
          citations, and academic contributions.
        </p>
        <div class="mt-4">
          <a href="https://scholar.google.com/citations?user={{ site.scholar_userid | default: 'YOUR_SCHOLAR_ID' }}" 
             class="btn btn-primary btn-lg px-4 py-2" 
             target="_blank" 
             rel="noopener noreferrer">
            <i class="ai ai-google-scholar mr-2"></i>
            View Google Scholar Profile
          </a>
        </div>
        <div class="mt-4">
          <small class="text-muted">
            <i class="fas fa-external-link-alt mr-1"></i>
            Opens in new tab
          </small>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="row mt-5">
  <div class="col-lg-12">
    <div class="card">
      <div class="card-header bg-light">
        <h5 class="mb-0">
          <i class="fas fa-info-circle mr-2"></i>
          Note
        </h5>
      </div>
      <div class="card-body">
        <p class="mb-0 text-muted">
          <strong>Setup Required:</strong> To link to your Google Scholar profile, 
          please update the <code>scholar_userid</code> field in your <code>_config.yml</code> file 
          with your actual Google Scholar user ID.
        </p>
        <div class="mt-3">
          <small class="text-muted">
            <i class="fas fa-code mr-1"></i>
            Example: <code>scholar_userid: abc123def456</code>
          </small>
        </div>
      </div>
    </div>
  </div>
</div>

<style>
.card {
  border: none;
  border-radius: 12px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(0,0,0,0.15) !important;
}

.btn {
  border-radius: 25px;
  font-weight: 500;
  transition: all 0.3s ease;
}

.btn:hover {
  transform: translateY(-1px);
  box-shadow: 0 4px 15px rgba(0,0,0,0.2);
}

.card-header {
  border-radius: 12px 12px 0 0 !important;
  border-bottom: 1px solid #e9ecef;
}

code {
  background-color: #f8f9fa;
  padding: 2px 6px;
  border-radius: 4px;
  font-size: 0.9em;
}
</style>
