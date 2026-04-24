# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project uses [Semantic Versioning](https://semver.org/).

## [0.1.0] - 2026-04-23

### Added

- Initial public repository release of **Mac System Probe**
- Classic Macintosh Pascal source for a System 6.0.8-era system information utility
- Native Toolbox-based interactive UI with:
  - left-side panel navigation
  - menus for Apple, File, and View
  - scrollable information display
- Panels for:
  - overview
  - memory
  - display
  - raw system IDs
  - about/help
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
