# About

This repository is made for my completely AI generated system info tool made by Codex, any changes will be listed as "by Codex" unless made by me will be listed as otherwise. This README.md is also generate by Codex.

AI is bound to make mistakes, so if any are found or is just plain unusable that is the reason. I do not know how Pascal works and created this purely out of curiousity. Feel free to take as you please and maybe I'll look more into how this programming language works.

![alt text](https://github.com/adamitronic/Mac-System-Probe/blob/main/ChatGPT%20Macintosh%20Plus.png "ChatGPT Macintosh Plus")

# Mac System Probe

**Mac System Probe** is a classic Macintosh Pascal utility for **System 6.0.8** and nearby **68K-era Mac environments**. It opens a native Toolbox window and presents detailed machine information through an interactive, period-appropriate UI instead of a plain text dump.

The app is written as a small resourceless Macintosh application in Pascal and is intended for use on real vintage Macs or in classic Mac emulators.

## Project Snapshot

- Native Toolbox UI with menus, radio-button navigation, and a scrollbar
- Multi-panel system reporting for hardware, memory, display, and raw IDs
- Built around `SysEnvirons` and `Gestalt`
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
- [`README.md`](./README.md): project overview, build notes, and usage guidance
- [`CHANGELOG.md`](./CHANGELOG.md): release history
- [`LICENSE`](./LICENSE): GNU GPL v3.0 license text
- [`.gitignore`](./.gitignore): ignore rules for metadata and build artifacts

## Requirements

To build the project, you will need a classic Macintosh Pascal environment with the standard Mac interfaces, such as:

- MPW Pascal
- THINK Pascal

The source expects the usual Macintosh interface units:

- `MemTypes`
- `QuickDraw`
- `OSIntf`
- `ToolIntf`
- `PackIntf`

## Building

1. Create a new classic Macintosh application project in your Pascal environment.
2. Add [`MacSystemProbe.p`](./MacSystemProbe.p) to the project.
3. Ensure the standard Macintosh Toolbox interface units are available to the compiler.
4. Build it as a 68K Macintosh application.

The UI is created directly in code, so there is no required `.r` resource file for the main window or menus.

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

The source has passed a Pascal compatibility-oriented syntax check in a modern validation workflow, but the program still needs full build-and-run confirmation in an authentic classic Macintosh development environment such as:

- Mini vMac
- THINK Pascal
- MPW Pascal
- real 68K Macintosh hardware

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

- Current version: [`0.1.0`](./CHANGELOG.md)
- License: [`GNU GPL v3.0`](./LICENSE)

## References

These references were used while shaping the source and compatibility assumptions:

- [Apple Technical Note OV16: Gestalt & _SysEnvirons - A Never-Ending Story](https://leopard-adc.pepas.com/technotes/ov/ov_16.html)
- [Inside Macintosh: Gestalt Manager](https://dev.os9.ca/techpubs/mac/OSUtilities/OSUtilities-10.html)
- [Inside Macintosh: The System Environment Record](https://dev.os9.ca/techpubs/mac/OSUtilities/OSUtilities-15.html)
- [Mac MPW Interfaces 1991 Pascal](https://mirrors.apple2.org.za/ftp.apple.asimov.net/documentation/macintosh/Mac%20MPW%20Interfaces%201991%20PASCAL.pdf)
