---
title: "Portfolio"
layout: default
permalink: /portfolio/
author_profile: false
---

<style>
  .aj-portfolio { max-width: 1180px; margin: 0 auto; padding: 4.5rem 1.5rem 4rem; }
  .aj-portfolio * { box-sizing: border-box; }
  .aj-portfolio-hero { padding: 2.6rem; border: 1px solid #dbe4f0; border-radius: 26px; background: linear-gradient(135deg, #ffffff 0%, #f4f7fc 100%); box-shadow: 0 18px 48px rgba(30,45,72,.07); }
  .aj-eyebrow { margin: 0 0 .75rem; color: #5168b7; font-size: .82rem; font-weight: 800; text-transform: uppercase; letter-spacing: .11em; }
  .aj-portfolio h1 { margin: 0; color: #1f2e46; font-size: clamp(2.3rem, 5vw, 4rem); line-height: 1.02; letter-spacing: -.05em; }
  .aj-lede { max-width: 860px; color: #445064; font-size: 1.18rem; line-height: 1.68; }
  .aj-pill-row { display: flex; flex-wrap: wrap; gap: .55rem; margin-top: 1.15rem; }
  .aj-pill-row span { padding: .45rem .7rem; border: 1px solid #dbe4f0; border-radius: 999px; background: #fff; color: #3f4f64; font-size: .86rem; font-weight: 700; }
  .aj-grid { display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 1.1rem; margin-top: 1.4rem; }
  .aj-card { display: flex; flex-direction: column; min-height: 270px; padding: 1.55rem; border: 1px solid #dbe4f0; border-radius: 22px; background: #ffffff; box-shadow: 0 18px 46px rgba(30,45,72,.07); }
  .aj-card-featured { grid-column: 1 / -1; background: linear-gradient(135deg, #ffffff 0%, #f6f8ff 100%); }
  .aj-label { margin: 0 0 .65rem; color: #5f7890; font-size: .74rem; font-weight: 900; text-transform: uppercase; letter-spacing: .1em; }
  .aj-card h2, .aj-card h3 { margin: 0 0 .7rem; color: #1f2e46; line-height: 1.18; letter-spacing: -.025em; }
  .aj-card a { color: #1f2e46 !important; text-decoration: none; }
  .aj-card a:hover { color: #5168b7 !important; text-decoration: underline; text-underline-offset: .15em; }
  .aj-card p { color: #4d596b; font-size: 1rem; line-height: 1.62; }
  .aj-card-link { margin-top: auto; align-self: flex-start; display: inline-flex; padding: .7rem .95rem; border-radius: 11px; background: #5168b7; color: #ffffff !important; font-weight: 800; text-decoration: none !important; }
  .aj-card-link:hover { background: #1f2e46; color: #ffffff !important; text-decoration: none !important; }
  @media (max-width: 800px) { .aj-portfolio { padding-top: 2.5rem; } .aj-grid { grid-template-columns: 1fr; } .aj-card-featured { grid-column: span 1; } }
</style>

<div class="aj-portfolio">
  <section class="aj-portfolio-hero">
    <p class="aj-eyebrow">Selected role-aligned case studies</p>
    <h1>Portfolio</h1>
    <p class="aj-lede">
      I design technical content systems that make complex developer, infrastructure, AI, OpenUSD, and emerging digital twin workflows easier to understand, validate, publish, discover, and reuse.
    </p>
    <div class="aj-pill-row">
      <span>Content workflow architecture</span>
      <span>OpenUSD readiness</span>
      <span>Metadata & taxonomy</span>
      <span>Validation readiness</span>
      <span>Publishing systems</span>
      <span>Developer enablement</span>
    </div>
  </section>

  <section class="aj-grid" aria-label="Portfolio case studies">
    <article class="aj-card aj-card-featured">
      <p class="aj-label">Featured case study</p>
      <h2><a href="{{ '/portfolio/content-workflow-architecture/' | relative_url }}">Content Workflow Architecture for Reusable Technical Assets</a></h2>
      <p>A role-aligned case study showing how I define metadata requirements, validation and readiness criteria, publishing workflows, lifecycle patterns, and contributor guidance for scalable technical content systems.</p>
      <a class="aj-card-link" href="{{ '/portfolio/content-workflow-architecture/' | relative_url }}">Read case study</a>
    </article>

    <article class="aj-card">
      <p class="aj-label">OpenUSD metadata & validation</p>
      <h3><a href="{{ '/portfolio/openusd-asset-metadata-validation/' | relative_url }}">OpenUSD Asset Metadata & Validation Readiness</a></h3>
      <p>A learning case study focused on metadata requirements, validation checks, readiness criteria, and catalog/search quality for reusable digital twin assets.</p>
      <a class="aj-card-link" href="{{ '/portfolio/openusd-asset-metadata-validation/' | relative_url }}">View OpenUSD case study</a>
    </article>

    <article class="aj-card">
      <p class="aj-label">OpenUSD publishing & discovery</p>
      <h3><a href="{{ '/portfolio/openusd-packaging-publishing/' | relative_url }}">OpenUSD Packaging, Publishing & Discovery Workflow</a></h3>
      <p>A contributor-ready workflow model for asset intake, packaging, validation, publishing, discovery, lifecycle updates, and reuse.</p>
      <a class="aj-card-link" href="{{ '/portfolio/openusd-packaging-publishing/' | relative_url }}">View workflow model</a>
    </article>

    <article class="aj-card">
      <p class="aj-label">OpenUSD / Omniverse learning</p>
      <h3><a href="{{ '/portfolio/omniverse-getting-started/' | relative_url }}">OpenUSD & Omniverse Kit Workflow Learning Project</a></h3>
      <p>A hands-on learning project focused on OpenUSD asset structure, composition, metadata, validation, packaging, publishing, and digital twin asset reuse.</p>
      <a class="aj-card-link" href="{{ '/portfolio/omniverse-getting-started/' | relative_url }}">View learning project</a>
    </article>

    <article class="aj-card">
      <p class="aj-label">Developer platform workflows</p>
      <h3><a href="{{ '/portfolio/walmart-content-workflows/' | relative_url }}">Walmart Marketplace API Content Workflow Architecture</a></h3>
      <p>Developer content workflows, metadata models, readiness scoring, reusable templates, AI-assisted authoring, and global API hub unification.</p>
      <a class="aj-card-link" href="{{ '/portfolio/walmart-content-workflows/' | relative_url }}">View case study</a>
    </article>

    <article class="aj-card">
      <p class="aj-label">Infrastructure documentation</p>
      <h3><a href="{{ '/portfolio/cisco-content-systems/' | relative_url }}">Cisco Infrastructure Content Systems</a></h3>
      <p>Docs-as-code, CI/CD publishing, API/SDK documentation, and release-aligned content operations for networking and server platforms.</p>
      <a class="aj-card-link" href="{{ '/portfolio/cisco-content-systems/' | relative_url }}">View case study</a>
    </article>

    <article class="aj-card">
      <p class="aj-label">AWS developer documentation</p>
      <h3><a href="{{ '/portfolio/aws-security-docs/' | relative_url }}">AWS Security Services Documentation Portfolio</a></h3>
      <p>API references, SDK examples, developer guides, knowledge-base artifacts, and workflow-based enablement for cloud security services.</p>
      <a class="aj-card-link" href="{{ '/portfolio/aws-security-docs/' | relative_url }}">View case study</a>
    </article>
  </section>
</div>
