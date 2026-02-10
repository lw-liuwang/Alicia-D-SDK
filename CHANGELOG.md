# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [v6.0.0] - 2025-02-10

### Added
- Added `fix_env/` directory with pre-configured URDF files for:
  - Alicia_D_v5_5
  - Alicia_D_v5_6
  - Alicia_M_v1_0
  - Bessica_M_v1_0

### Changed
- Simplified README.md to quick start guide
- Updated requirements.txt to use fixed versions:
  - synria-robocore==1.0.0
  - synriard==1.0.0
- Changed from GitHub installation to PyPI versions for better stability

### Fixed
- Fixed URDF compatibility issues between different environments
- Added Alicia_D_v5_6 support with gripper_50mm and gripper_100mm variants
- Added comprehensive fix instructions in README.md

### Known Issues
- Alicia_D_v5_5 only supports 100mm gripper (no 50mm variant available)
