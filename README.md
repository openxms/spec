# XMS Specification

**XMS (eXchange Metadata Standard)** defines a lightweight `key=value;...` format for attaching metadata to virtual currency transactions in kromer.

## Quick Start

XMS metadata strings follow this format:

- **XMS v1+**: `xms/1;key=value;another=value`
- **CommonMeta (v0)**: `key=value;another=value` (fallback)

```
xms/1;username=steve;useruuid=550e8400;ref.item="diamond_sword";return=k123456789
```

## Documentation

- **[Specification](/spec/)** - Complete XMS format specification
- **[Examples](/examples/)** - Usage examples and test cases
- **[Extensions](/extensions/)** - Custom key documentation

## Current Version

**Version 0.0.1** - Released 2025-10-02

See [CHANGELOG.md](CHANGELOG.md) for version history.

## Key Features

- ✅ Lightweight `key=value;` syntax
- ✅ Nested object support with dot notation
- ✅ Array support with numeric indices
- ✅ Graceful fallback to CommonMeta format
- ✅ Common keys for user, item, message, return, error
- ✅ Type coercion support (optional)
- ✅ Performance optimized (max 5 nesting levels)

## Common Keys

| Key        | Purpose                      | Example                 |
| ---------- | ---------------------------- | ----------------------- |
| `username` | User's in-game name          | `username=steve`        |
| `useruuid` | User's UUID                  | `useruuid=550e8400...`  |
| `message`  | User message (255 chars max) | `message="Hello world"` |
| `return`   | Return address/callback      | `return=k123456789`     |
| `error.*`  | Error information            | `error.code=404`        |

## License

This specification is released under [MIT License](LICENSE).
