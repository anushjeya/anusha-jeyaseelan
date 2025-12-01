---
layout: single
title: "Creating a Custom Omniverse Kit Extension"
permalink: /omniverse/kit-extension/
classes: wide            # use full width, less wasted space
sidebar:
  nav: omniverse_docs    # uses the Omniverse sidebar nav
author_profile: false
toc: true
toc_sticky: true

---
This tutorial walks you through creating a new Omniverse Kit extension, adding a simple user interface, and scripting a basic interaction with a 3D USD scene.
## Set up the extension project
The easiest way to create a new extension is to use the Omniverse Kit command-line extension generator.
### Generate the extension
Navigate to your Omniverse Kit App directory and run:
```bash
./kit-sdk/kit --create-extension omni.my_first_extension
```
This command generates a new folder named `omni.my_first_extension` under your app's `exts` directory.
### Inspect the generated files
Your new extension contains two important files:
<ul>
<li><code>extension.toml</code> - Defines metadata such as name, version, dependencies, and UI category.</li>
<li><code>omni/my_first_extension/extension.py</code> - The main Python file where your extension logic runs.</li>
</ul>
All UI elements are created using the `omni.ui` framework inside the `extension.py` file.

## Build an user interface 
Omniverse Kit uses the `omni.ui` framework for building lightweight, reactive UI.
### Open the extension folder
Inside your extension folder, open `extension.py`
```bash
exts/omni.my_first_extension/omni/my_first_extension/extension.py
```
### Add a Basic Window
Import the UI module and create a small dockable window inside the `on_startup()` method:
```bash
import omni.ext
import omni.ui as ui

class MyExtension(omni.ext.IExt):
    def on_startup(self, ext_id):
        self._window = ui.Window("My First Extension", width=300, height=300)

        with self._window.frame:
            with ui.VStack():
                ui.Label("Welcome to my custom tool!")
                # Button will be added soon

    def on_shutdown(self):
        self._window = None
```
### Clean up properly
Always clear UI resources in `on_shutdown()` to prevent memory leaks.

## Interact with USD
This section details the instructions to create a sphere in the Universal Screen Description (USD) stage to create geometry.
### Import USD utilities 
At the top of the file, import the required problems for UI and scene manipulation.
### Create the action function
Add this helper function inside your extension class:
```bash
def create_sphere(self):
    stage = omni.usd.get_context().get_stage()
    sphere_path = "/World/MyNewSphere"

    omni.kit.commands.execute(
        "CreateMeshPrimWithDefaultXform",
        prim_type="Sphere",
        prim_path=sphere_path,
    )

    print(f"Created sphere at: {sphere_path}")
```
### Connect the Button
Ensure your button is linked to this function. Update your UI code:
```bash
with self._window.frame:
    with ui.VStack():
        ui.Label("Welcome to my custom tool!")
        ui.Button("Create a Sphere", clicked_fn=self.create_sphere)
```

## Launch and test 
### Launch Your Kit App
Start the custom Kit App you created previously. Use your app launcher:
```bash
./repo.bat app
```
### Enable your extension
Inside the Omniverse kit, do the following:
<ol>
<li>Open <b>Windows</b> > <b>Extensions</b>.</li>
<li>Search for your extension by its name. For example, <code>my.sphere.generator</code></li>
<li>Click the checkbox to enable it. Your new Sphere Creator Tool window will appear.</li>
</ol>

### Test the functionality
Click the <b>Create Sphere in Scene</b> button. A new sphere should instantly appear in the viewport and in the Stage window, demonstrating that your custom code is now integrated into the Omniverse platform.