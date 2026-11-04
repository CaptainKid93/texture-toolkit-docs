# Channel Shuffle

**Channel Shuffle** builds **one new RGB or RGBA Texture2D** from channels of **one source texture**. You can reorder, duplicate or omit existing source channels, or set output channels to a constant.

It does **not** combine multiple Texture2D assets.

## Source and mapping

1. Select a `Texture2D` and open **Texture Toolkit → Channel Shuffle**.
2. Use the native source picker if needed. If multiple textures were selected, choose **one source** explicitly.
3. Map output **R, G and B** independently to an available source channel, **Constant 0** or **Constant 1**.
4. Enable optional **Alpha** if the output needs RGBA and choose its mapping.
5. Choose the new asset name and destination `/Game` folder.
6. Select **Preview**, inspect the proposed output, then **Create Texture**.

The default output name is `<SourceAssetName>_Shuffled`. The initial destination is based on the selected source/folder, and subsequent browsing does not silently change it. Name and destination remain editable.

## Example

For an RGBA source you can map **output R ← source G**, **output G ← source B**, **output B ← source R**. Available channels and constants depend on actual Source Art; the tool does not invent source channels.

## Safety and quality

- The source asset is not replaced.
- Unsupported or missing Source Art, unavailable channels, dirty sources, invalid destinations and output collisions can block Create Texture.
- Changes to source, mapping, output type, name or destination invalidate the previous Preview.
- The pipeline checks generated TGA channel values and compares imported Source Art where possible.
- GPU compression, mipmaps and filtering can still affect the visible result. Visual identity to the source is **not** guaranteed.
- On success, **Show in Content Browser** can locate the created asset.

There is no separate **Channel Composer** or multi-source packing workflow in this version.

[Extract Channel](extract-channel.md) · [Troubleshooting](../troubleshooting.md)
