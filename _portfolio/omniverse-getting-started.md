---
layout: single
title: "Omniverse Getting Started Guide (GSG)"
permalink: /omniverse/overview/
classes: wide            # use full width, less wasted space
sidebar:
  nav: omniverse_docs    # uses the Omniverse sidebar nav
author_profile: false
toc: true
toc_sticky: true

---

## 1. What you’ll build

This guide walks you through creating your first Omniverse Kit-based application on windows using NVIDIA’s official Kit App Template. By the end, you will:

- Install the core Omniverse tools you need
- Clone the Kit App Template repo
- Generate a new Kit-based app with `repo.bat template new`
- Run and verify your app on Windows
- Know where to start customizing behavior with extensions

This is aimed at developers who are comfortable with the command line but new to Omniverse Kit.

---

## 2. Prerequisites

Before you start, make sure you have:

- Supported NVIDIA GPU with recent drivers
- Windows 10/11
- NVIDIA Omniverse Launcher installed and logged in
- At least one Kit-based Omniverse app installed (for example, *Omniverse Code* or *USD Composer*)
- Git installed and available in your `PATH`
- PowerShell or Command Prompt

> Tip: Open PowerShell as your main terminal for this tutorial. You can search for “PowerShell” in the Start menu and choose *Windows PowerShell* or *PowerShell 7*.

---

## 3. Set up your workspace

Pick a folder where you keep your dev projects. For example:

```powershell cd C:\Users\<your-name>\dev```

If this dev folder does not exist yet, create it:

```mkdir C:\Users\<your-name>\dev
cd C:\Users\<your-name>\dev
```

Replace `<your-name>` with your actual Windows username.
