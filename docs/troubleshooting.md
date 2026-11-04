# Troubleshooting

## Texture Toolkit is missing from the context menu

- Select **one or more Texture2D assets only**. Mixed selections containing non-Texture2D assets do not expose the submenu.
- Check that the plugin and required Editor dependencies are enabled.
- Look under the native **Texture Actions** group of the Content Browser asset context menu, not under an old standalone Texture Toolkit section.
- Restart Unreal Editor if you just enabled the plugin.

## Review has no eligible candidates

The review may report **Blocked** or **Unchanged** items. Read each blocked reason and resolve the specific issue; an asset that cannot run one operation may still be eligible for another.

Typical reasons include missing/unreadable Source Art, unsupported source format or precision, unavailable Alpha/channel, invalid destination, already-existing output asset or unsaved/dirty source package.

## Final action is disabled or my Preview is stale

After changing an input, source, mapping, name or destination, run **Review** or **Preview** again. The plugin deliberately rejects execution based on obsolete inputs.

## I cannot find a newly generated asset

Output paths vary:

- **Export / Resize:** external folder selected in the popup.
- **Strip Alpha:** a `ProcessedTextures` folder under the active Content Browser folder.
- **Extract Channel:** **same Unreal folder as the individual source texture**.
- **Channel Shuffle:** selected `/Game` destination; use **Show in Content Browser** after success.

## Source File path changed, but the change did not persist

With Export's optional Source File update or Resize's optional Reimport, **save the changed Unreal Texture2D package manually**. Writing the external file does not automatically save the Unreal asset.

## Channel looks different inside Unreal

Imported Source Art and GPU-visible data are not identical by definition. Compression settings, mip selection, filtering and view scale can affect appearance. Compare the original channel data, generated file and imported Source Art first. A visual difference alone does not establish where the pipeline changed data.

## Problem persists

Check **Unreal Output Log** for Texture Toolkit messages. For a reproducible report, include plugin version, exact engine version, operation, source format/dimensions, intended destination, review error and non-sensitive log excerpt. Do not share private/client asset data.

[Compatibility & Limitations](compatibility.md)
