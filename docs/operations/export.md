# Export

**Export** writes selected `Texture2D` assets as **PNG** or **TGA** files to a chosen **external folder**. It does not create new Unreal assets.

## Steps

1. Select `Texture2D` assets in the Content Browser and open **Texture Toolkit → Export**.
2. Set the format and destination folder.
3. Decide whether to enable **Overwrite existing files**.
4. Optionally enable **Update source file path**, which updates import metadata on successfully exported Unreal textures.
5. Select **Review Export** to inspect candidate, blocked and unchanged counts.
6. Select **Export N Textures** to execute.

## Outputs and safety

- An existing external file is not overwritten unless the explicit option is enabled.
- The review does not generate the export files.
- When **Update source file path** is enabled, successfully exported textures have their import path changed and become **dirty**; manually save those Unreal assets to persist the path.
- TGA depth follows stored pixel data: G8 → 8-bit grayscale, fully opaque four-channel data → 24-bit RGB, non-opaque Alpha → 32-bit RGBA.
- G16 TGA export is blocked to avoid silently losing source precision.
- Unsupported source data, invalid destinations and collisions are reported for the affected assets.

Export does **not** promise to preserve the appearance of GPU-compressed mips exactly. See [Compatibility & Limitations](../compatibility.md).

[First workflow](../getting-started.md) · [Troubleshooting](../troubleshooting.md)
