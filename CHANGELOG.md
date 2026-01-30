# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- Add GitHub Actions CI/CD workflow for automated build and release

### Changed

- Upgrade wujihand-upgrader-core dependency to v1.1.1

## [4.1.0] - 2026-01-12

### Added

- Add post-upgrade guidance prompt on completion screen (close program, power cycle device)

### Fixed

- Display full release notes on OTA home page instead of collapsed view

## [4.0.0] - 2025-12-31

### Added

- Enhance device connection logging

### Changed

- Rename binary from wujihand-ota to wujihand-upgrader
- Rename organization from Wuji-Technology-Co-Ltd to wuji-technology

### Fixed

- Fix device update check issues and React key warnings
- Fix firmware version extraction logic
- Replace hardcoded Chinese error messages with i18n internationalization
- Comprehensive improvements to firmware version handling and error display

[Unreleased]: https://github.com/wuji-technology/wujihand-upgrader/compare/v4.1.0...HEAD
[4.1.0]: https://github.com/wuji-technology/wujihand-upgrader/compare/v4.0.0...v4.1.0
[4.0.0]: https://github.com/wuji-technology/wujihand-upgrader/releases/tag/v4.0.0
