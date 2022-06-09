# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [1.5.0] - 2022-06-09
### Changed
- Moved dependencies to include file to avoid race conditions with hosts vars.

## [1.4.2] - 2022-02-22
### Fixed
- Adapted for CentOS derived distros. Related to ansible/main#263

## [1.4.1] - 2022-02-17
### Changed
- Changed testing images.

## [1.4.0] - 2022-01-26
### Changed
- Supported distros. Related to ansible/main#178

## [1.3.3] - 2022-02-13
### Fixed
- Fixed problem managing NetworkManager service during cleanup.

## [1.3.2] - 2021-12-22
### Fixed
- Fixed minimum versions required and proxy dependency.
