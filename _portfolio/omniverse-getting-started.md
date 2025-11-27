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
Before you start the installation process, make sure you have:
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
You will be prompted for a few values, for instance:
<ul>
<li>App name - The name for the Kit-based app. For example, first_app</li>
<li>Destination folder - You can either choose the default folder or any folder of your choice.</li>
</ul>

## 6. Explore the folder/project structure
Open the app folder in your editor, such as Visual Studio Code. 
<ul>
  <li>apps/&lt;your_app_name&gt;.kit – The main configuration file that defines your Omniverse application. It specifies which extensions to load, window layout, and startup settings.</li>
  <li>exts/ – A folder where your custom extensions live. Each extension is its own package with:
    <ul>
      <li>config/extension.toml – Defines extension metadata, load behavior, and required dependencies for Omniverse Kit.</li>
      <li>exts/&lt;extension_name&gt;/ – Python files that define the behavior of your Omniverse extension.</li>
    </ul>
  </li>
  <li>logs/ – Created after you run the app. Contains runtime logs useful for debugging startup failures.</li>
</ul>

## 7. Run your app 

In your Windows command terminal, from the root of your generated app repo, run:

```bash
.\repo.bat test
```

This command launches your Kit-based app using the `.kit` file generated earlier. Logs and errors if any, are printed in the terminal. An Omniverse windows opens up. 

To verify if the installation is successful, ensure that the title or app name matches the name you chose and the Omniverse viewport is open. 

If the app fails to start: 
<ul>
<li>Check the terminal output in Visual Studio Code for Python or config errors.</li>
<li>Review the files in the <code>logs/</code> directory.</li>
<li>Fix any missing paths or extensions, then run the <code>.\repo.bat test</code> again.</li>
</ul>

## 8. Try your first customization
One of the easiest ways to customize your app is by choosing which extensions your app loads.
<ol>
<li>Open your app's <code>.kit</code> file. For example, <code>apps/my_kit_app.kit</code></li>
<li>Look for a section named <code>[settings.app.exts]</code></li>
<li>You can add or remove extensions here. <code>"omni.kit.window.console" = {}</code></li>
<li>Save the file and rerun <code>.\repo.bat test</code></li>
</ol>
If the console extension is enabled, you’ll see an additional console window or menu entry, depending on your configuration.
> Tip: The `.kit` file is your app’s composition root: it controls which pieces of functionality (extensions) are brought together to form your application.

## Next steps 
Create your own extension under `exts/` and register it in your `.kit` file.
Add a custom menu item, tool window, or viewport overlay. Integrate Omniverse features such as USD scene loading or RTX rendering. 
This is a solid foundation for a more advanced tutorial where you walk through building a specific tool or workflow inside Omniverse Kit.
