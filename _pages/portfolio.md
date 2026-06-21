---
title: "Portfolio"
layout: single
permalink: /portfolio/
author_profile: true
---

<style>
.portfolio-hero {
  padding: 1.25rem 1.5rem;
  border: 1px solid #d9e2ec;
  border-radius: 14px;
  background: #f7fbff;
  margin-bottom: 1.5rem;
}
.portfolio-hero h2 {
  margin-top: 0;
  margin-bottom: .5rem;
}
.portfolio-tags {
  display: flex;
  flex-wrap: wrap;
  gap: .4rem;
  margin-top: .9rem;
}
.portfolio-tag {
  font-size: .72rem;
  line-height: 1;
  border: 1px solid #bcccdc;
  border-radius: 999px;
  padding: .35rem .55rem;
  background: #fff;
}
.featured-card {
  border: 1px solid #9fb3c8;
  border-radius: 16px;
  padding: 1.3rem 1.5rem;
  background: #ffffff;
  box-shadow: 0 2px 8px rgba(16, 42, 67, .08);
  margin: 1.25rem 0 1.75rem;
}
.featured-card h3, .portfolio-card h3 {
  margin-top: 0;
  margin-bottom: .5rem;
}
.featured-card p, .portfolio-card p {
  margin-bottom: .8rem;
}
.portfolio-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1rem;
  margin-top: 1rem;
}
.portfolio-card {
  border: 1px solid #d9e2ec;
  border-radius: 14px;
  padding: 1.1rem 1.2rem;
  background: #fff;
}
.portfolio-card:hover {
  box-shadow: 0 2px 10px rgba(16, 42, 67, .09);
}
.card-meta {
  display: block;
  font-size: .75rem;
  letter-spacing: .02em;
  text-transform: uppercase;
  color: #52616b;
  font-weight: 700;
  margin-bottom: .45rem;
}
.card-link {
  font-weight: 700;
}
</style>

<div class="portfolio-hero">
  <h2>Selected case studies and writing samples</h2>
  <p>I design technical content systems that turn fragmented developer, infrastructure, and AI workflows into structured, validated, reusable, and discoverable experiences.</p>
  <div class="portfolio-tags">
    <span class="portfolio-tag">Content workflow architecture</span>
    <span class="portfolio-tag">Metadata & taxonomy</span>
    <span class="portfolio-tag">Validation readiness</span>
    <span class="portfolio-tag">Docs-as-code</span>
    <span class="portfolio-tag">API & SDK docs</span>
    <span class="portfolio-tag">AI-assisted authoring</span>
    <span class="portfolio-tag">OpenUSD learning</span>
  </div>
</div>

<div class="featured-card">
  <span class="card-meta">Featured case study</span>
  <h3><a href="{{ site.baseurl }}/portfolio/content-workflow-architecture/">Content Workflow Architecture for Reusable Technical Assets</a></h3>
  <p>A role-aligned case study showing how I define metadata requirements, validation/readiness standards, publishing workflows, lifecycle patterns, and contributor guidance for scalable technical content systems.</p>
  <a class="card-link" href="{{ site.baseurl }}/portfolio/content-workflow-architecture/">Read the case study →</a>
</div>

<div class="portfolio-grid">
  <div class="portfolio-card">
    <span class="card-meta">Developer platform workflows</span>
    <h3><a href="{{ site.baseurl }}/portfolio/walmart-content-workflows/">Walmart Marketplace API Content Workflow Architecture</a></h3>
    <p>Developer content workflows, metadata models, readiness scoring, reusable templates, AI-assisted authoring, and global API hub unification.</p>
    <a class="card-link" href="{{ site.baseurl }}/portfolio/walmart-content-workflows/">View case study →</a>
  </div>

  <div class="portfolio-card">
    <span class="card-meta">OpenUSD / Omniverse learning</span>
    <h3><a href="{{ site.baseurl }}/portfolio/omniverse-getting-started/">OpenUSD & Omniverse Kit Learning Project</a></h3>
    <p>A hands-on learning project focused on OpenUSD asset structure, composition, metadata, validation, packaging, and publishing concepts.</p>
    <a class="card-link" href="{{ site.baseurl }}/portfolio/omniverse-getting-started/">View learning project →</a>
  </div>

  <div class="portfolio-card">
    <span class="card-meta">AI developer enablement</span>
    <h3><a href="{{ site.baseurl }}/portfolio/claude-doc/">Claude Code Developer Enablement Guide</a></h3>
    <p>Structured guidance for AI-assisted coding workflows, prompt/action templates, configuration patterns, and developer onboarding.</p>
    <a class="card-link" href="{{ site.baseurl }}/portfolio/claude-doc/">View project →</a>
  </div>

  <div class="portfolio-card">
    <span class="card-meta">AWS developer documentation</span>
    <h3><a href="{{ site.baseurl }}/portfolio/aws-security-docs/">AWS Security Services Documentation Portfolio</a></h3>
    <p>API references, SDK examples, developer guides, knowledge base artifacts, and workflow-based enablement for cloud security services.</p>
    <a class="card-link" href="{{ site.baseurl }}/portfolio/aws-security-docs/">View case study →</a>
  </div>

  <div class="portfolio-card">
    <span class="card-meta">Infrastructure documentation</span>
    <h3><a href="{{ site.baseurl }}/portfolio/cisco-content-systems/">Cisco Infrastructure Content Systems</a></h3>
    <p>Docs-as-code, CI/CD publishing, API/SDK documentation, and release-aligned content operations for networking and server platforms.</p>
    <a class="card-link" href="{{ site.baseurl }}/portfolio/cisco-content-systems/">View case study →</a>
  </div>

  <div class="portfolio-card">
    <span class="card-meta">Executable tutorial</span>
    <h3><a href="{{ site.baseurl }}/portfolio/aws-sagemaker/">End-to-End Image Classification with Amazon SageMaker</a></h3>
    <p>A hands-on tutorial demonstrating dataset preparation, S3 integration, training, deployment, and step-by-step developer guidance.</p>
    <a class="card-link" href="{{ site.baseurl }}/portfolio/aws-sagemaker/">View tutorial →</a>
  </div>
</div>
