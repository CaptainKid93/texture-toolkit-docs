# Resize

**Resize** exports downscaled PNG/TGA files. You can optionally **reimport** them into the existing Unreal `Texture2D` assets.

## Configure

1. Select one or more `Texture2D` assets and open **Texture Toolkit → Resize**.
2. Choose the maximum target side. The available presets are **16, 32, 64, 128, 256, 512, 1024, 2048, 4096 and 8192**.
3. Select PNG or TGA and the external destination.
4. Decide whether to use **Reimport and update file path**.
5. Select **Review Resize**; inspect blocked assets and the destination/reimport summary.
6. Select **Resize N Textures** (export only) or **Resize & Reimport N**.

## How sizing works

- Resize **preserves the aspect ratio**.
- It does **not** enlarge an image above its original dimensions.
- Only the maximum side is selected from power-of-two presets; the other side may be non-power-of-two. For example: **1024 × 768 → 512 × 384**.
- The output folder mirrors the relevant `/Game` hierarchy beneath the chosen external destination.

## Two modes

| Mode | Effect on existing Unreal assets |
| --- | --- |
| **Export only** | Creates reduced external files; existing Texture2D assets are not reimported. |
| **Reimport and update file path** | Reimports into the **same existing Texture2D** and updates its Source File path. Save the changed Unreal packages manually. |

External file overwrite is controlled separately. Review potential changes before enabling Reimport; the plugin is not a substitute for source control or backups.

The QA "standard texture sides" policy is informational and **independent** of Resize target presets.

[Export](export.md) · [Troubleshooting](../troubleshooting.md)
