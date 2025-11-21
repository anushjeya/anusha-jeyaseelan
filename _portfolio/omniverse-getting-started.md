---
title: "Getting Started with an Omniverse Kit-Based App (Using kit-app-template)"
layout: single
toc: false
tags: [omniverse, kit, tutorial]
## image: /assets/images/claude.png
description: "Getting started documentation for creating Omniverse Kit-based app from the official NVIDIA Kit App template."
links:
  - name: View Project
    url: https://github.com/anushjeya/omniverse-first-extension


## What this tutorial covers

In this short guide, I show how to:

- Create an Omniverse Kit-based app from the official **Kit App Template**
- Run it on Windows
- Make a tiny Python change so you know where to customize it

This is the same workflow Omniverse developers use: start from a template, then layer on extensions and behavior.

---

## Prerequisites

- NVIDIA Omniverse installed (Launcher + at least one Kit-based app, like USD Composer or Code)
- Git and Python 3.x
- Windows (PowerShell or cmd)

---

## 1. Create the app from the template

From a terminal:

```powershell
cd C:\Users\<you>\dev
git clone https://github.com/NVIDIA-Omniverse/kit-app-template.git
cd kit-app-template
.\repo.bat template new

When prompted:

Template type: app

App name: anusha.hello.app (or your preferred name)

Title: something like Anusha Hello App

This generates a small Kit app plus a .kit file that defines its configuration.

## Run the app


