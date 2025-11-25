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
This guide walks you through creating your first NVIDIA Omniverse Kit-App based application on windows using NVIDIA’s official Kit App Template using the command line. By the end, you will:
- Install the core Omniverse tools you need
- Clone the Kit App Template repo
- Generate a new Kit-based app with `repo.bat template new`
- Run and verify your app on Windows
- Know where to start customizing behavior with extensions

## 2. Prerequisites
Before you start the installation process,  make sure you have:
- Supported NVIDIA GPU with recent drivers
- Windows 10/11
- NVIDIA Omniverse Launcher installed and logged in
- At least one Kit-based Omniverse app installed (for example, *Omniverse Code* or *USD Composer*)
- Git installed and available in your `PATH`
- PowerShell or Command Prompt
> Tip: Open PowerShell as your main terminal for this tutorial. You can search for “PowerShell” in the Start menu and choose *Windows PowerShell* or *PowerShell 7*.

## 3. Set up your workspace
Pick a folder where you keep want to install the Kit App Template. For example:
```bash
cd C:\Users\<your-name>\dev
```
If you want to create a new folder, use:
```bash
mkdir C:\Users\<your-name>\dev 
cd C:\Users\<your-name>\dev
```
Replace `<your-name>` with your actual Windows username.
## 4. Clone the NVIDIA Kit App Template 
Clone the official Kit App Template repository into your dev folder. Navigate into your new `dev` directory and clone the official template repository. 

The following command downloads the Kit App Template into your local folder. You should now see files such as ```repo.bat```, ```source/```, ```apps/```, and ```exts/```.

```bash
git clone https://github.com/NVIDIA-Omniverse/kit-app-template.git
cd kit-app-template
```
## 5. Create a new NVIDIA Kit-based app from the template 
The Kit App template includes a helper script, ```repo.bat``` which builds out the new app for you. 
Ensure you are in the ```kit-app-template``` folder and run:
```bash
.\repo.bat template new
```

