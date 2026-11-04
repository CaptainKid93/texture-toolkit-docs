# Strip Alpha

**Strip Alpha** creates processed copies of applicable selected textures **without Alpha**. It does not rewrite the original Texture2D or its external source file.

## Use it

1. Select one or more `Texture2D` assets in the Content Browser.
2. Right-click → **Texture Toolkit → Strip Alpha**.
3. Read the applicability/collision summary and the short confirmation.
4. Confirm to create the processed outputs, or decline to leave everything unchanged.

Unlike the other operations, **Strip Alpha has no configuration popup** and does not use the Review → Execute window.

## Where outputs go

Processed Unreal assets are created under **`ProcessedTextures`** within the active Content Browser folder. If the active folder is already inside a `ProcessedTextures` tree, the existing processed root is reused rather than nested again.

## Safety and limitations

- A texture without a removable Alpha channel may be reported as not needing the operation.
- Unreadable source pixels, unsupported formats, missing metadata or output collisions can prevent processing of an affected asset.
- Existing Unreal assets are not silently overwritten.
- Inspect Unreal's **Output Log** for per-asset details and completion results.

**Strip Alpha** is not the same operation as [Extract Channel](extract-channel.md). Extraction creates **one grayscale asset beside each source**, not under `ProcessedTextures`.

[Getting Started](../getting-started.md)
