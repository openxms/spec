# Namespace Conventions

## Overview

XMS uses dot notation to create logical namespaces for keys. This document provides conventions for organizing custom keys in a consistent and maintainable way.

## Common Namespaces

These namespaces are recommended for common use cases:

- `error.*` - Error information

### Common Top-Level Keys

- `username` - User's in-game name, max 16 chars (string, optional)
- `useruuid` - User's UUID with/without dashes (string, optional)
- `message` - User messages (255 chars max, string, optional)
- `return` - Return address/callback (string, optional)
- `error` - Simple error message (string, optional)

## Recommended Namespace Patterns

### Feature-Based Organization

Group related functionality under feature namespaces:

```
inventory.slot.0=sword
inventory.slot.1=shield
inventory.capacity=20

payment.method=credit_card
payment.currency=USD
payment.amount=29.99

analytics.event=purchase
analytics.session=abc123
analytics.timestamp=1633024800
```

## Nesting Guidelines

### Maximum Depth

Remember the 5-level nesting limit:

```
✅ Valid:   level1.level2.level3
```
