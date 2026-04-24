# About

This repository is made for my completely AI generated system info tool made by Codex, any changes will be listed as "by Codex" unless made by me will be listed as otherwise. This README.md is also generate by Codex.

AI is bound to make mistakes, so if any are found or is just plain unusable that is the reason. I do not know how Pascal works and created this purely out of curiousity. Feel free to take as you please and maybe I'll look more into how this programming language works.

![alt text](https://github.com/adamitronic/Mac-System-Probe/blob/main/ChatGPT%20Macintosh%20Plus.png "ChatGPT Macintosh Plus")

# Mac System Probe

**Mac System Probe** is a classic Macintosh Pascal utility for **System 6.0.8** and nearby **68K-era Mac environments**. It opens a native Toolbox window and presents detailed machine information through an interactive, period-appropriate UI instead of a plain text dump.

The app is written in classic Macintosh Pascal and is intended for use on real vintage Macs or in classic Mac emulators. The main window and controls are still created in code, and the project now also includes an optional resource file for menus and an About alert.

## Project Snapshot

- Native Toolbox UI with menus, radio-button navigation, and a scrollbar
- Multi-panel system reporting for hardware, memory, display, and raw IDs
- Built around `SysEnvirons` and `Gestalt`
- Includes optional Rez resources for menu bar and About UI
- Source-first release aimed at real vintage Mac and emulator workflows

## Features

- Native Macintosh Toolbox window with menus, panel switching, and scrolling
- `SysEnvirons` support for broad System 6 compatibility
- `Gestalt` queries for deeper hardware and software identification when available
- Memory Manager reporting including `FreeMem`, `MaxMem`, `CompactMem`, and `PurgeSpace`
- Screen and QuickDraw reporting including bounds, menu bar height, and version details
- Raw selector reporting for comparing machines, ROMs, and emulator configurations
- Refresh command so the displayed data can be rescanned without restarting the app

## Panels

- `Overview`: machine, CPU, keyboard, System version, ROM, RAM, and general environment data
- `Memory`: live Memory Manager statistics plus MMU and FPU reporting
- `Display`: screen bounds, menu bar height, row bytes, and QuickDraw details
- `Raw IDs`: low-level `SysEnvirons` and `Gestalt` values in numeric and hex form
- `About`: built-in help and usage notes

## Why This Exists

System 6-era Macs can expose useful hardware and software details, but the experience is often fragmented across low-level APIs, ad hoc utilities, or emulator-specific reporting. This project packages that information into a single small application with a UI that feels at home on a late-1980s Macintosh.

## Repository Contents

- [`MacSystemProbe.p`](./MacSystemProbe.p): Pascal source for the application
- [`MacSystemProbe.r`](./MacSystemProbe.r): Rez-format UI resources for menus, menu bar, and About alert
- [`MacSystemProbe-classic.txt`](./MacSystemProbe-classic.txt): classic Mac line-ending transfer copy of the Pascal source
- [`MacSystemProbe-resource-classic.txt`](./MacSystemProbe-resource-classic.txt): classic Mac line-ending transfer copy of the Rez source
- [`README.md`](./README.md): project overview, build notes, and usage guidance
- [`CHANGELOG.md`](./CHANGELOG.md): release history
- [`LICENSE`](./LICENSE): GNU GPL v3.0 license text
- [`.gitignore`](./.gitignore): ignore rules for metadata and build artifacts

## Requirements

To build the project, you will need a classic Macintosh Pascal environment such as:

- MPW Pascal
- THINK Pascal

For THINK Pascal 4.0 specifically:

- the Toolbox interfaces are treated as built in, so the source does **not** include a `USES` list for them
- the easiest import path is to create a new source file in THINK Pascal and paste in [`MacSystemProbe-classic.txt`](./MacSystemProbe-classic.txt)

For MPW Pascal:

- you may need to adapt the source back toward explicit interface-unit usage depending on your installed interfaces and project setup

## Building

1. Create a new classic Macintosh application project in your Pascal environment.
2. Add [`MacSystemProbe.p`](./MacSystemProbe.p) to the project.
3. Add [`MacSystemProbe.r`](./MacSystemProbe.r) if you want resource-based menus and the About alert compiled into the application.
4. If you are using THINK Pascal 4.0, prefer importing from [`MacSystemProbe-classic.txt`](./MacSystemProbe-classic.txt) and saving the file from inside THINK Pascal.
5. Build it as a 68K Macintosh application.

The main window and controls are created in code. The optional resource file supplies the menu bar, menu definitions, and About alert so the app can use a more traditional Macintosh resource-fork UI setup.

If you need to transfer files into a classic Mac environment, use:

- [`MacSystemProbe-classic.txt`](./MacSystemProbe-classic.txt) for the Pascal source
- [`MacSystemProbe-resource-classic.txt`](./MacSystemProbe-resource-classic.txt) for the resource source

## Running

Mac System Probe is intended for:

- real 68K Macintosh systems running System 6.0.8 or similar
- emulators such as Mini vMac, Basilisk II, and other vintage Mac environments

Once launched, you can:

- click the left-side radio buttons to switch panels
- use the `View` menu to jump between panels
- use the scrollbar to browse longer reports
- press `Command-R` to refresh the displayed data
- press `Command-Q` to quit

## Compatibility Notes

- `SysEnvirons` provides the base layer of information needed for System 6-class machines.
- `Gestalt` was introduced in System 6.0.4, so a real System 6.0.8 machine should normally support it.
- Some individual `Gestalt` selectors may still be missing depending on ROM version, hardware generation, or emulator implementation.
- When a selector is unavailable, the program reports the failure instead of crashing.

## Validation Status

This repository is currently a **source release**.

The current validation status is:

- [`MacSystemProbe.p`](./MacSystemProbe.p) passed a Pascal compatibility-oriented syntax/structure check in a modern local workflow
- [`MacSystemProbe.r`](./MacSystemProbe.r) has been added and reviewed, but has not been fully validated in a classic Macintosh Rez setup from this workspace
- the full application still needs build-and-run confirmation in an authentic classic Macintosh development environment such as Mini vMac, THINK Pascal, MPW Pascal, or real 68K Macintosh hardware

## Design Notes

- The source is intentionally written in an old-school Macintosh Pascal style to stay close to period development tools.
- The UI is monochrome-friendly and should work on compact black-and-white Macs as well as later color-capable systems.
- The app favors robust fallback reporting over making assumptions from a single hardware identifier.

## Roadmap

Possible next steps for the project:

- add fuller disk and mounted volume reporting
- create a dedicated MPW Pascal project layout
- create a dedicated THINK Pascal project version
- add icons, alerts, or optional resource-based polish
- extend the machine database for more late-68K models
- capture screenshots from an authentic emulator setup

## Release Info

- Current version: [`0.2.0`](./CHANGELOG.md)
- License: [`GNU GPL v3.0`](./LICENSE)

## References

These references were used while shaping the source and compatibility assumptions:

- [Apple Technical Note OV16: Gestalt & _SysEnvirons - A Never-Ending Story](https://leopard-adc.pepas.com/technotes/ov/ov_16.html)
- [Inside Macintosh: Gestalt Manager](https://dev.os9.ca/techpubs/mac/OSUtilities/OSUtilities-10.html)
- [Inside Macintosh: The System Environment Record](https://dev.os9.ca/techpubs/mac/OSUtilities/OSUtilities-15.html)
- [Mac MPW Interfaces 1991 Pascal](https://mirrors.apple2.org.za/ftp.apple.asimov.net/documentation/macintosh/Mac%20MPW%20Interfaces%201991%20PASCAL.pdf)
