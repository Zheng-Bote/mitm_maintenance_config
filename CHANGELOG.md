# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.0] - 2026-09-23
### Added
- Initial release of the `mitm_maintenance_config` CLI utility.
- Support for encrypting and decrypting JSON configuration files (`-d` flag for decryption).
- Secure password prompt implementation using `golang.org/x/term` to prevent password echoing in the terminal.
- Strict JSON format validation for configuration files during encryption.
- Secure file operations (written with `0600` permissions) for output files.
