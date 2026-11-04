# Extract Channel

**Extract Channel** creates **one new grayscale Texture2D per eligible source**, using the selected source channel. The original `Texture2D` remains unchanged.

## Supported source channels

| Imported Source Art | Choices |
| --- | --- |
| 8-bit BGRA8 / RGBA8 | **R, G, B, A** |
| 8-bit G8 | **Gray** |
| G16, HDR/float, unsupported or unreadable source | Extraction blocked for that asset with a specific reason |

A channel is available only when the source actually supports it. The tool does not pretend that grayscale or unavailable formats contain separate RGB/Alpha channels.

## Use it

1. Select one or more `Texture2D` assets in the Content Browser, including assets **from different folders**.
2. Open **Texture Toolkit → Extract Channel**.
3. Choose **R, G, B, A** or **Gray** as available.
4. Accept or edit **Output Suffix**. Defaults are `_R`, `_G`, `_B`, `_Alpha`, and `_Gray`. A suffix manually edited by the artist is retained when changing channels.
5. Select **Review Extraction**, inspect eligible and blocked assets, then **Extract N Textures**.

## Example: output beside each source

| Source asset | Selected channel | New asset |
| --- | --- | --- |
| `/Game/Rocks/T_Rock_ORM` | G | `/Game/Rocks/T_Rock_ORM_G` |
| `/Game/Wood/T_Wood_ORM` | G | `/Game/Wood/T_Wood_ORM_G` |

**No new Unreal folders are created.** The destination derives from **each source Texture2D's own package path**, not the active Content Browser folder. Existing output assets are never overwritten.

## Data fidelity and limits

Extraction targets the original selected 8-bit channel values, not a resized or automatically gamma-adjusted version. The pipeline verifies byte-level output and, when available, imported Source Art. Unreal's GPU compression, mipmaps, and preview display may still look different; pixel-source fidelity and GPU appearance are **separate** questions.

[Channel Shuffle](channel-shuffle.md) · [Compatibility](../compatibility.md)
