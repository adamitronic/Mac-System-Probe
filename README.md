# Mac System Probe

`MacSystemProbe.p` is a classic Macintosh Pascal program aimed at **Mac System 6.0.8** and similar late-68000 / early-68030 environments.

It opens a real Toolbox window with:

- left-side interactive section buttons
- a scrollable information pane
- Apple, File, and View menus
- refresh and quit commands

The program reports:

- machine, CPU, keyboard, and basic environment data from `SysEnvirons`
- enhanced hardware/software IDs from `Gestalt` when available
- memory-manager statistics like `FreeMem`, `MaxMem`, `CompactMem`, and `PurgeSpace`
- screen geometry and QuickDraw version info
- raw selector values that are handy when comparing real Macs vs emulators

## Target toolchains

This source is written in an old-school Macintosh Pascal style that should be closest to:

- MPW Pascal with the standard Mac interfaces
- THINK Pascal with equivalent Toolbox units

## Build notes

1. Create a normal Macintosh application project.
2. Add [`MacSystemProbe.p`](/Users/adamhansenjr/Documents/Codex/2026-04-23/could-you-write-a-program-in/MacSystemProbe.p).
3. Make sure the usual Macintosh units are available:
   `MemTypes`, `QuickDraw`, `OSIntf`, `ToolIntf`, `PackIntf`
4. Build as a 68K Macintosh application.

The source is intentionally **resourceless** for the main UI, so you do not need a separate `.r` file just to get the window and menus on screen.

## Controls

- Click the radio buttons on the left to switch sections.
- Use the View menu to jump between panels.
- Drag or click the scrollbar to move through long reports.
- Press `Command-R` to refresh.
- Press `Command-Q` to quit.

## Compatibility notes

- `SysEnvirons` provides the baseline data needed for System 6 class machines.
- `Gestalt` was introduced in System 6.0.4, so on a real **System 6.0.8** machine those calls should normally be available.
- Some individual selectors may still fail on older ROMs or simplified emulator setups; the UI reports that rather than crashing.

I could also turn this into:

- a stricter THINK Pascal project version
- an MPW Pascal project layout
- a version with fuller disk/volume enumeration
- a black-and-white-only UI styled more like a shipping 1989 utility
