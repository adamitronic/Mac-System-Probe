# Mac System Probe

Mac System Probe is a classic Macintosh Pascal utility for **System 6.0.8** and nearby 68K-era environments. It opens a native Toolbox window and presents detailed machine information through an interactive, period-appropriate UI instead of a plain text dump.

The app is written as a small resourceless Macintosh application in Pascal and is intended for use on real vintage Macs or in classic Mac emulators.

## Features

- Native Macintosh Toolbox window with menus, radio-button navigation, and a scrollbar
- Multi-panel interface for browsing different categories of system information
- `SysEnvirons` support for baseline System 6 compatibility
- `Gestalt` queries for deeper hardware and software identification when available
- Memory Manager stats such as `FreeMem`, `MaxMem`, `CompactMem`, and `PurgeSpace`
- Screen and QuickDraw details including geometry and reported graphics version
- Raw selector values for comparing ROMs, machines, and emulator configurations
- Refresh command so the information can be rescanned without restarting the app

## Panels

The program currently includes these views:

- `Overview`: machine, CPU, keyboard, System version, ROM, RAM, and general environment data
- `Memory`: live Memory Manager statistics and MMU/FPU information
- `Display`: screen bounds, menu bar height, row bytes, and QuickDraw details
- `Raw IDs`: low-level `SysEnvirons` and `Gestalt` values in numeric and hex form
- `About`: built-in help and usage notes

## Why This Exists

System 6-era Macs can expose useful hardware and software details, but the experience is usually fragmented across low-level APIs, ad hoc tools, or emulator-specific reporting. This project packages that information into a single small application with a UI that feels at home on a late-1980s Macintosh.

## Repository Contents

- [`MacSystemProbe.p`](./MacSystemProbe.p): the Pascal source for the application
- [`README.md`](./README.md): project overview, build notes, and compatibility guidance

## Requirements

To build the project you will need a classic Macintosh Pascal environment with the standard Mac interfaces, such as:

- MPW Pascal
- THINK Pascal

The source expects common Macintosh interface units including:

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

Mac System Probe is meant for:

- real 68K Macintosh systems running System 6.0.8 or similar
- emulators such as Mini vMac, Basilisk II, or other vintage Mac environments

Once launched, you can:

- click the left-side radio buttons to switch panels
- use the `View` menu to jump between panels
- use the scrollbar to browse longer reports
- press `Command-R` to refresh the data
- press `Command-Q` to quit

## Compatibility Notes

- `SysEnvirons` provides the base layer of information needed for System 6-class machines.
- `Gestalt` was introduced in System 6.0.4, so a real System 6.0.8 machine should normally support it.
- Some specific `Gestalt` selectors may still be missing depending on ROM version, hardware generation, or emulator implementation.
- When a selector is unavailable, the program reports the failure instead of crashing.

## Design Notes

- The source is intentionally written in an old-school Macintosh Pascal style to stay close to period development tools.
- The UI is monochrome-friendly and should work on compact black-and-white Macs as well as later color-capable systems.
- The app favors robustness over trying to infer too much from any single hardware identifier.

## Current Status

This repository currently contains source code only. It has not been compiled inside this workspace because no classic Macintosh Pascal toolchain is installed here. The code is meant to be imported into a real vintage Mac development setup or an emulator configured with one.

## Future Improvements

Possible next steps for the project:

- add fuller disk and mounted volume reporting
- create a dedicated MPW Pascal project layout
- create a dedicated THINK Pascal project version
- add icons, alerts, or optional resource-based polish
- extend the machine database for more late-68K models

## References

These references were used while shaping the source and compatibility assumptions:

- [Apple Technical Note OV16: Gestalt & _SysEnvirons - A Never-Ending Story](https://leopard-adc.pepas.com/technotes/ov/ov_16.html)
- [Inside Macintosh: Gestalt Manager](https://dev.os9.ca/techpubs/mac/OSUtilities/OSUtilities-10.html)
- [Inside Macintosh: The System Environment Record](https://dev.os9.ca/techpubs/mac/OSUtilities/OSUtilities-15.html)
- [Mac MPW Interfaces 1991 Pascal](https://mirrors.apple2.org.za/ftp.apple.asimov.net/documentation/macintosh/Mac%20MPW%20Interfaces%201991%20PASCAL.pdf)

## License

This project is licensed under the **GNU General Public License v3.0**.

You may copy, modify, and redistribute this software under the terms of the GPL-3.0 license. If you distribute modified versions, you must also make the corresponding source code available under the same license terms.

For the full license text, see the GNU project page:

- [GNU General Public License v3.0](https://www.gnu.org/licenses/gpl-3.0.en.html)
