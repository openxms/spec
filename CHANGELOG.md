# Changelog

All notable changes to the XMS specification will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Romantic Versioning](https://romversioning.github.io/romver/).

## [0.0.1] - 2025-10-03

### Added

- Initial XMS v0.0.1 specification
- Version marker format: `xms/N;`
- Common key definitions for system refs and errors
- Nested object support with dot notation
- Array support with numeric indices
- CommonMeta fallback behavior for malformed XMS
- Type coercion guidelines (optional)
- Performance considerations (5-level nesting limit)
- Input sanitization and security guidelines
- Comprehensive examples and test cases

### Specification Details

- Maximum nesting depth: 5 levels
- Username limit: 16 characters
- Message limit: 255 characters
- Key pattern: `[a-z0-9_.]+`
- Escape sequences: `\"` and `\\` in quoted values

## [Unreleased]

### Planned

- Additional commonly used keys based on community feedback
- Extended error handling mechanisms
- Performance benchmarking guidelines
