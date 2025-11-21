---
layout: splash
title: "Anusha Jeyaseelan"
permalink: /

header:
  overlay_color: "#000"
  overlay_filter: 0.3
  overlay_image: "/assets/images/hero-bg.jpg"
  actions:
    - label: "View My Portfolio"
      url: "/portfolio/"
      icon: "fas fa-folder-open"

excerpt: "Technical Writer · Cloud & Developer Infrastructure"

intro:
  - excerpt: "I’m a technical writer and content strategist specializing in cloud, developer infrastructure, and API documentation. I love turning complex systems into clear, actionable content for developers."

feature_row:
  - image_path: "/assets/images/omniverse-thumb.jpg"
    alt: "NVIDIA Omniverse Tutorial"
    title: "Getting Started with an Omniverse Kit-Based App"
    excerpt: "Create your first Omniverse Kit-based app from the official Kit App template and customize it with extensions."
    url: "/portfolio/omniverse-getting-started/"
    btn_label: "Read case study"
    btn_class: "btn--primary"
  - image_path: "/assets/images/claude-thumb.jpg"
    alt: "Claude Code Documentation"
    title: "Claude Code Documentation"
    excerpt: "Developer docs for agentic coding workflows."
    url: "/portfolio/claude-doc/"
    btn_label: "Read case study"
    btn_class: "btn--primary"
  - image_path: "/assets/images/sagemaker-thumb.jpg"
    alt: "AWS SageMaker Tutorial"
    title: "AWS SageMaker Image Classification"
    excerpt: "End-to-end tutorial walking through S3 data prep, training, and deployment on Amazon SageMaker."
    url: "/portfolio/aws-sagemaker/"
    btn_label: "Read case study"
    btn_class: "btn--primary"
---

{% include feature_row id="intro" type="center" %}
{% include feature_row id="feature_row" %}
