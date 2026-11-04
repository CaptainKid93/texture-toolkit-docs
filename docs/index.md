# Texture Toolkit for Unreal Artists

**Less texture busywork. More creative work.**

Texture Toolkit brings focused `Texture2D` operations into **Unreal Editor's Content Browser**. Select textures, choose an operation and review eligible outputs before committing changes.

**Status:** **Private Beta · In Validation**. The plugin is implemented for **Unreal Engine 5.0.3, Windows x64**, but the latest distributable build still requires final end-to-end Editor certification. This documentation is a preview, not a claim of public release.

## What you can do

| Operation | Result |
| --- | --- |
| [Export](operations/export.md) | Batch-export selected Texture2D assets as PNG or TGA files. |
| [Resize](operations/resize.md) | Downscale textures to exported PNG/TGA files, optionally reimporting into existing assets. |
| [Strip Alpha](operations/strip-alpha.md) | Create processed copies without the Alpha channel. |
| [Extract Channel](operations/extract-channel.md) | Create grayscale Texture2D assets from individual R, G, B, A or Gray source channels. |
| [Channel Shuffle](operations/channel-shuffle.md) | Rearrange channels from **one** source Texture2D into a new RGB/RGBA texture. |

## Designed for the Editor

- Launch operations from the **Texture Toolkit** submenu in the native **Texture Actions** context menu.
- Each operation has an independent Slate popup, except **Strip Alpha**, which uses direct confirmation.
- **Review** (or **Preview** for Channel Shuffle) precedes the execution action.
- Unsupported inputs and destination conflicts are reported rather than silently modified.
- Output locations and the effect on original assets depend on the operation; read the operation guide before execution.

Start with [Installation](installation.md), then follow the [first workflow](getting-started.md). For current support boundaries, see [Compatibility & Limitations](compatibility.md).

!!! note "Planned features are not included"
    Smart Naming, HDR/EXR processing and multi-source channel packing are **not** advertised as available. The former Channel Composer operation has been retired.
