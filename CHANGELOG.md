# Changelog

## Unreleased — 2026-10-12

- Physically validated Nobara / Proton 9.0-4f / REPENTOGON 1.1.3 on the G14:
  all treatments, toggles, gameplay, room transition, restart, Alt+Tab, resizing,
  persistence, normal shutdown, and removal restoring untreated REPENTOGON play.
- Isolate pre-existing presentation GL errors before the mod's own GL work,
  fixing treatment disabling during the tested Proton fullscreen startup.
  Own rendering errors still fail normally; steady Off remains GL-work-free.
  No shader or preset changes. Windows physical regression of this fix is pending.
- Document the tested child-executable DLL placement, prefix override and exact
  retained REPENTOGON Steam launch options, with platform-specific limits.
- Optional LCD ghosting using the original response shader, canonical strength
  and seven-frame history. No preset or shader retuning.
- F6 toggles ghosting on LCD Light/Strong; CRT/VHS curvature and the F7 treatment
  cycle are unchanged. The existing toast shows the LCD variant and On/Off state.
- Ghosting defaults Off and is saved independently of curvature, shared between
  LCD variants. History is initialized on enable and invalidated on disable,
  treatment changes, resizing and GL-context recreation. Disabled ghosting does
  not allocate or update history textures.
- Validated both LCD variants On/Off in Repentance+ on the main PC: movement,
  shooting, treatment switching, resizing, persistence and normal shutdown.
  Forced in-process context recreation and long-session testing remain unverified.
- No release published.

## 0.1.0 — 2026-10-12 — local experimental build

- Standalone x86 OpenGL integration for Repentance+, including direct GDI
  presentation and Epic-overlay resolver/shutdown safeguards.
- Original CRT Core, CRT Studio, LCD Light, LCD Strong and four-stage VHS
  treatments, plus pass-free Off.
- Flat/Curved CRT and VHS presentation without bezel or reflection features.
- Fixed logical-grid phase with dynamic output dimensions and source sampling
  kept separate; fractional-resolution positioning retained.
- F7 treatment cycle, F6 curvature, sharp 1.5-second notifications and saved
  selections.
- Real-game local validation; documentation and captures prepared. No release
  published. Further hardware, native-mod coexistence and long-session testing
  remains outside the initial validation scope.
