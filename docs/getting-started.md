# Getting Started

## First workflow: export selected textures

1. Open the Content Browser and select one or more `Texture2D` assets.
2. Right-click and choose **Texture Toolkit → Export** in the native **Texture Actions** group.
3. Choose **PNG** or **TGA** and the external destination folder.
4. Review the **Overwrite existing files** and **Update source file path** options.
5. Select **Review Export**. Review shows **Candidates**, **Blocked** and **Unchanged** counts, plus reasons for blocked textures; it does not write the exported files.
6. Select **Export N Textures** to process eligible candidates.
7. Check progress and results. If you opted to update the **Source File path**, save the affected Unreal assets manually.

There is no executable final action when the review has zero eligible candidates.

## The common operation flow

| Step | Export / Resize / Extract Channel | Channel Shuffle |
| --- | --- | --- |
| Configure | Source selection and operation inputs | One source asset, channel mapping and destination |
| Check | **Review Export / Resize / Extraction** | **Preview** |
| Execute | **Export / Resize / Extract N Textures** | **Create Texture** |
| Change something | **Back** keeps inputs; review again | A changed mapping/source/name needs a new Preview |

**Strip Alpha** is different: it checks applicability and asks for a short confirmation without opening a dedicated operation popup.

Each operation window captures the selection when opened. Reopening the same operation focuses its existing window; different operations may remain open concurrently. Jobs that create assets are serialized.

## Keep source changes intentional

- **Export** produces external files; a separate option can update source import paths.
- **Resize** produces external files; **Reimport** can also update the original Unreal Texture2D.
- **Strip Alpha**, **Extract Channel** and **Channel Shuffle** create new assets without replacing the original Texture2D.
- **Cancel** stops after the active item and **does not undo** already completed results.

For exact output locations and constraints, open the corresponding [operation guide](index.md#what-you-can-do).
