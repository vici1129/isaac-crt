# Workshop companion draft

Not uploaded. Awaiting approval and physical testing. This is an optional,
no-op Lua companion, not the native graphics mod or an installer.

## Files

- `isaac-crt/metadata.xml`: display name **Isaac CRT**, directory `isaac-crt`,
  version `0.1.0`, draft description, and **Private** visibility. No Workshop
  item ID is assigned; do not invent one or copy another item's ID.
- `isaac-crt/main.lua`: only `RegisterMod("Isaac CRT", 1)`. The `1` is Isaac's
  Lua API version. No callbacks, globals added by this script, dependencies,
  file access, DLL loading, or Lua/native communication.
- `isaac-crt/preview.png`: byte-for-byte copy of
  `../assets/workshop-thumbnail.png`, the approved 512x512 PNG. For a later,
  separately approved upload, select this image in ModUploader's preview field;
  including the file does not itself assign a Steam preview.
- `DESCRIPTION.txt`: editable Steam BBCode draft, also embedded verbatim in
  metadata. Keep both descriptions in sync before any eventual upload.

## Quick local test (manual)

1. Close Isaac. In Steam, use **Properties > Installed Files > Browse**.
2. Copy this directory's **`isaac-crt` subfolder** into the game's `mods`
   directory. The result must be `mods/isaac-crt/main.lua` and
   `mods/isaac-crt/metadata.xml`, not an extra nested `workshop` folder.
   Stop if `mods/isaac-crt` already exists; do not overwrite it.
   With an alternate launcher, use the mods directory loaded by that game.
3. Launch normally. Look for **Isaac CRT** in the Mods menu and enable it.
   Confirm there are no companion-related Lua errors. It should add no UI,
   messages, items, hotkeys, or gameplay behavior. Standard game restrictions
   on enabled mods still apply; use an appropriate test save.
4. Disable it and confirm the native treatment remains independent. Without
   the DLL installed, this companion alone must not produce any graphics effect.
   With the DLL installed, F6/F7 continue to belong to the DLL, not Lua.
5. Close Isaac and remove only the copied `mods/isaac-crt` folder to remove the
   local companion. Leave the native DLL, other mods, settings, and saves alone.

No DLL installation or replacement is needed to test the companion's menu entry.
Do not put `opengl32.dll` in the companion folder. See the repository's
[installation guide](../INSTALL.txt) for the separate native graphics mod.

## Local validation

Checked metadata XML parsing, name/directory/API registration consistency,
description equality, the three-file payload, and the thumbnail's PNG dimensions
and byte identity. The Lua entry point was statically checked to contain only
the registration call; it was not executed in Isaac. No game or ModUploader
launch, Workshop upload, GitHub Release, or physical compatibility test was run.

The repository currently documents no published native release. The draft links
to the future release location and does not claim a download already exists.
Review download availability and complete the manual checks before publishing.

Format references: the installed game's `resources/scripts/main.lua` and mod
metadata, the [IsaacDocs example project](https://wofsauge.github.io/IsaacDocs/rep/tutorials/ExampleProject.html),
and the [IsaacScript publishing guide](https://isaacscript.github.io/main/publishing-to-the-workshop/).
