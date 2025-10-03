# XMS Extensions

This directory documents the extension mechanism for XMS and provides guidelines for custom key implementations.

## Documentation

- **[Namespace Conventions](namespace-conventions.md)** - Guidelines for custom namespaces
- **[Custom Keys](custom-keys.md)** - Documentation of known custom key implementations

## Extension Philosophy

XMS is designed to be extensible while maintaining backward compatibility. The core specification defines common keys for various use cases, but applications can define their own keys following these principles:

### Forward Compatibility

- Unknown keys are preserved during parsing
- Parsers should not fail on unrecognized keys
- New keys should not conflict with common keys

### Namespace Organization

- Use dot notation for logical grouping: `myapp.setting=value`
- Consider using prefixes for major features: `game.inventory.slot1=sword`
- Avoid overly deep nesting (remember the 5-level limit)

### Documentation Requirements

- Document all custom keys used in your implementation
- Provide examples of usage
- Specify any validation rules or size limits
- Consider contributing useful keys back to the core specification

## Contributing Extensions

If you develop useful custom keys that could benefit the broader XMS ecosystem:

1. Document the keys thoroughly
2. Provide usage examples
3. Consider proposing them for inclusion in future XMS versions
4. Share implementations with the community

## Compatibility Guidelines

### Do:

- Use descriptive, lowercase key names
- Follow dot notation conventions
- Document key purposes and constraints
- Test with multiple XMS parser implementations

### Don't:

- Conflict with common keys (`username`, `message`, `error`, etc.)
- Exceed nesting depth limits
- Use characters outside `[a-z0-9_.]`
- Create circular references or complex data types

## Example Extensions

### Gaming Applications

```
game.level=5
game.inventory.0=sword
game.inventory.1=shield
game.stats.health=100
game.stats.mana=50
```

### E-commerce Systems

```
order.id=12345
order.items.0.name=widget
order.items.0.quantity=2
order.shipping.method=express
order.payment.type=credit_card
```

### Analytics Tracking

```
analytics.session=abc123
analytics.event=purchase
analytics.category=gaming
analytics.value=29.99
```
