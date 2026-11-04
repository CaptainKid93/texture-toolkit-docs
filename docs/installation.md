# Installation

Texture Toolkit is an **Editor-only plugin**, not a runtime component for packaged games.

## Requirements

- **Unreal Engine 5.0.3** is the development target. Final release-package verification is still pending.
- **Windows x64**.
- An Unreal-compatible **C++ build toolchain**, if the package requires compilation.
- Unreal's **PythonScriptPlugin** and **EditorScriptingUtilities** plugins enabled.
- A project in which you can install a project-level Editor plugin.

Texture Toolkit bundles **Pillow 9.5.0** for Unreal's Python 3.9 environment. You do not need a separate standalone image-processing application.

## Install in a project

1. Close Unreal Editor.
2. Copy the complete plugin directory to `<YourProject>/Plugins/TextureToolkit`.
3. Reopen the project. Allow the Editor module to compile if prompted.
4. In **Edit → Plugins**, enable **Texture Toolkit for Unreal Artists** and its Editor dependencies.
5. Restart the Editor if prompted.
6. In the Content Browser, select one or more **Texture2D** assets, right-click and open **Texture Toolkit**.

The context submenu is available only when every selected asset is a `Texture2D`. A mixed selection with another asset type does not show it.

## After installation

Read [Getting Started](getting-started.md) for a first export. **Settings** and **About** are available from the main Unreal Editor **Texture Toolkit** menu.

For confirmed engine support and known limitations of a distributable package, consult the release-specific compatibility information. **Do not assume support for other Unreal Engine versions.**

[Compatibility & Limitations](compatibility.md) · [Troubleshooting](troubleshooting.md)
