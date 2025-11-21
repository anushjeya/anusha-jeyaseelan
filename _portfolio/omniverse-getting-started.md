---
layout: single
title: "Omniverse Getting Started Guide (GSG)"
description: "Comprehensive developer documentation for Claude Code at Anthropic."
links:
  - name: View Project
    url: https://github.com/anusha/claude-doc
toc: false
tags: [omniverse, kit, getting-started]
---

## 1. What is Omniverse Kit?

NVIDIA Omniverse is a platform for building OpenUSD and RTX-powered applications.

**Omniverse Kit** is the SDK used to build those desktop and cloud apps. This guide shows the quickest path to:

- Clone the official **Kit App Template**
- Create your own Kit-based app
- Run it locally on Windows

---

## 2. Prerequisites

- NVIDIA GPU with recent drivers
- NVIDIA Omniverse installed (Launcher + at least one Kit-based app, e.g., USD Composer or Code)
- Git and Python 3.x installed
- Windows (PowerShell or Command Prompt)

---

## 3. Clone the Kit App Template

Open PowerShell or Command Prompt and choose a folder for your dev work:

```powershell
cd C:\Users\<your-name>\dev
git clone https://github.com/NVIDIA-Omniverse/kit-app-template.git
cd kit-app-template

