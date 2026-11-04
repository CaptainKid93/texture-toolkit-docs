# Settings

Open **Texture Toolkit → Settings** from Unreal Editor's **main menu**.

Settings control informational quality checks and selected artist preferences. **A QA warning is not an automatic processing prohibition.** Each operation independently checks whether it can safely process a texture.

## Validation

The current Settings UI includes:

- **Standard Texture Sides:** a QA policy for preferred dimensions; it does **not** restrict Resize's separate target list.
- **Power of Two:** informational QA check.
- **Warn when Alpha is present (QA only):** reports Alpha as a QA concern without automatically removing or blocking it.
- **Required Aspect Ratio:** optional QA check; leave empty to disable.

Unknown Unreal dimension/Alpha metadata must remain unknown rather than being guessed.

## Naming

The current Naming section includes:

- **Check Naming Convention**: opt-in QA validation.
- **Naming Prefix** and **Naming Descriptors**: values for the existing QA naming convention.

The QA naming settings do **not** automatically rename textures, force an output name or enable a standalone Renamer.

**Smart Naming** (configurable output suffix presets and packed ORM/RMA name suggestions) is **planned**, not implemented in this private-beta build.

## Saving preferences

Artist overrides are stored within the project under `Saved/TextureToolkit/settings.json`. Project defaults are stored in the plugin configuration. Use **Save Settings** or **Restore Project Defaults** as appropriate.

Operational changes require a fresh Review/Preview. QA-only changes must not silently change pixel processing or block unrelated operations.

[Compatibility](compatibility.md)
