# Changelog

All notable changes to this project are documented here. Follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) and [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.8.3] - 2026-03-26

### Fixed

- `.linq` files can now be opened in diff mode (Git diff, Copilot diff) without being hijacked into a standalone editor tab. The auto-redirect introduced in 1.8.1 (which moved every `.linq` file to Editor Group 1) was removed because it also fired for diff editors, immediately replacing the diff view with a regular tab. Opening `.linq` files from the LINQPad Explorer still opens them in Editor Group 1 as before.

> **Note on original intent (1.8.1):** The auto-redirect was added to prevent `.linq` files from opening *over* the Interactive Results Viewer. Because the Results Viewer opens as a webview panel in `ViewColumn.Beside` (Group 2), clicking a file while the viewer had focus would place the new editor in Group 2 as well, obscuring the viewer. The redirect solved this by ensuring scripts always land in Group 1. The side-effect of breaking diff mode outweighs this convenience, so the redirect has been removed. If a `.linq` file opens in Group 2, simply drag its tab to Group 1.

## [1.8.2] - 2026-03-24

### Fixed

- Pressing F5 or Ctrl+F5 on a `.linq` file now runs the LINQPad script instead of triggering VS Code's debugger (which previously opened the Extension Marketplace asking for a LinqPad debugger extension)

## [1.8.1] - 2025-11-10

### Added

- Real-time streaming output to Interactive Results Viewer
- Stop button to terminate running scripts
- Running indicator (green dot) when script is executing
- Error output (stderr) now displays in viewer with ⚠️ label
- Auto-redirect: .linq files always open in Editor Group 1

### Changed

- Viewer updates in real-time as output arrives (no more waiting for completion)
- Removed "Loading..." placeholder - shows "Waiting for output..." instead
- Output streams immediately like console (no complex buffering)
- .linq files automatically move to Group 1 even when opened from other groups

### Fixed

- Viewer now shows compilation errors and warnings (stderr)
- .linq files no longer open in Group 2 when Results Viewer is visible
- Consistent editor group behavior regardless of active panel

## [1.8.0] - 2025-11-07

### Added

- Query Folders Explorer pane in sidebar
- Open Files section showing currently opened .linq files
- Close All Open Files button on Open Files section
- Favorites system: star/unstar files, shows at top
- Search/filter files across all sections and folders
- New Script button in toolbar for quick file creation
- Auto-detects query locations from LINQPad client configuration
- Real-time updates when opening/closing files

### Changed

- Only shows folders configured in LINQPad client (no hardcoded paths)
- Improved file organization with collapsible sections

### Fixed

- Open Files section now tracks only visible editors
- Proper refresh on file open/close events

## [1.7.8] - 2025-11-01

- UI: Action buttons replaced with links (Close | Clear | Copy)
- Split location toggle hidden
- 'Running viewer' indicator removed after results
- Bugfixes and polish for narrow UI

## [1.7.7] - 2025-11-01

- Documentation cleanup and formatting improvements

## [1.7.1] - 2025-11-01

- Maintenance: GitHub links corrected

## [1.7.0] - 2025-01-08

- Interactive Results Viewer
- JSON tree visualization
- Sortable tables, CSV export
- Collapsible sections, multi-tab support

## [1.6.1] - 2024-12-15

- F12 navigation
- #load file support
- NuGet package links
- IntelliSense features

## [1.6.0] - 2024-11-01

- C# syntax highlighting
- One-click execution
- Command palette integration
