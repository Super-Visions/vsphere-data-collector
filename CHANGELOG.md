# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).
Git tags for this project use the `sv-v` prefix (e.g. `sv-v1.0.0`) to avoid collisions with upstream tags.

## [Unreleased]

### Added

- **Upstream:** Collect status of Datastores
- **Upstream:** Improve module installation checks by using integrated methods

### Changed

- Incorporated [upstream 1.4.0][upstream-1.4.0]
- Uses [collector base 1.5.1][base-1.5.1]

### Fixed

- **Upstream:** Compatibility with absence of Datacenter Management
- **Upstream:** Compatibility with absence of Advanced Storage Management
- **Upstream:** Compatibility with absence of Network Management Extended
- **Upstream:** Attribute `logicalvolumes_list` is actually not sync'ed on Hypervisors and VMs
- **Upstream:** Compatibility with PHP 8.4

[Unreleased]: https://github.com/Super-Visions/vsphere-data-collector/compare/1.4.0...HEAD
[upstream-1.4.0]: https://github.com/Combodo/itop-data-collector-vsphere/releases/tag/1.4.0
[base-1.5.1]: https://github.com/Combodo/itop-data-collector-base/releases/tag/1.5.1
