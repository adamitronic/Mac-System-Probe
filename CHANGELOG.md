# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project uses [Semantic Versioning](https://semver.org/).

## [0.2.0] - 2026-04-24

### Added

- Optional Rez resource file in `MacSystemProbe.r` for menu bar, menus, and About alert UI
- Classic Mac transfer copies in `MacSystemProbe-classic.txt` and `MacSystemProbe-resource-classic.txt`
- Updated documentation for THINK Pascal 4.0 import and transfer workflow
- Additional validation coverage for the current Pascal source structure

### Changed

- Updated the Pascal source to better fit THINK Pascal 4.0 expectations by removing Toolbox interface units from the top-level source file
- Updated the application to use resource-based menus and About UI when the corresponding resources are present, while keeping code-based fallback behavior
- Refined the README to document resource support, transfer files, build guidance, and current validation status

### Notes

- `MacSystemProbe.p` passed a modern Pascal compatibility-oriented syntax and structure validation pass
- `MacSystemProbe.r` has been added and reviewed but still needs validation in an authentic classic Macintosh Rez workflow
- Full build-and-run confirmation on vintage Mac hardware or a period-correct emulator setup remains a next-step milestone

## [0.1.0] - 2026-04-23

### Added

- Initial public repository release of **Mac System Probe**
- Classic Macintosh Pascal source for a System 6.0.8-era system information utility
- Native Toolbox-based interactive UI with left-side panel navigation
- Menus for Apple, File, and View
- Scrollable information display
- Panels for overview, memory, display, raw system IDs, and about/help
- System reporting based on `SysEnvirons` and `Gestalt`
- Memory-related reporting using `FreeMem`, `MaxMem`, `CompactMem`, and `PurgeSpace`
- Repository documentation in `README.md`
- Project license in `LICENSE` using the GNU General Public License v3.0
- Repo `.gitignore` covering macOS metadata, Windows metadata, and Pascal build artifacts

### Changed

- Improved source compatibility for Pascal syntax validation workflows
- Refined repository structure for a clean first public release

### Notes

- This release has passed a modern Pascal compatibility-oriented syntax check
- Authentic target validation in a classic Macintosh environment remains a next-step milestone
