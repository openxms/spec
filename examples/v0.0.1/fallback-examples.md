# CommonMeta Fallback Examples - XMS v0.0.1

## Basic CommonMeta Format

**Input:**

```
username=steve;useruuid=550e8400e29b41d4a716446655440000;return=k123456789;diamond_sword
```

**Output:**

```json
{
  "version": 0, // CommonMeta format
  "isFallback": true, // Indicates fallback parsing
  "entries": [
    { "name": "username", "value": "steve" },
    { "name": "useruuid", "value": "550e8400e29b41d4a716446655440000" },
    { "name": "return", "value": "k123456789" },
    { "name": "diamond_sword", "value": "" }
  ],
  "data": {
    "username": "steve",
    "useruuid": "550e8400e29b41d4a716446655440000",
    "return": "k123456789",
    "diamond_sword": ""
  }
}
```

## Malformed XMS Triggers Fallback

**Input:**

```
xms/1;username=steve;message="unterminated quote;return=k123
```

**Output:**

```json
{
  "version": 0,
  "isFallback": true,
  "entries": [
    { "name": "xms/1", "value": "" },
    { "name": "username", "value": "steve" },
    { "name": "message", "value": "\"unterminated quote" },
    { "name": "return", "value": "k123" }
  ],
  "data": {
    "xms/1": "",
    "username": "steve",
    "message": "\"unterminated quote",
    "return": "k123"
  }
}
```

## Simple Error Message

**Input:**

```
error=You must purchase at least one of this product!
```

**Output:**

```json
{
  "version": 0,
  "isFallback": true,
  "entries": [
    {
      "name": "error",
      "value": "You must purchase at least one of this product!"
    }
  ],
  "data": {
    "error": "You must purchase at least one of this product!"
  }
}
```

## Bare Tokens (CommonMeta Only)

**Input:**

```
slime;iron;gold
```

**Output:**

```json
{
  "version": 0,
  "isFallback": true,
  "entries": [
    { "name": "slime", "value": "" },
    { "name": "iron", "value": "" },
    { "name": "gold", "value": "" }
  ],
  "data": {
    "slime": "",
    "iron": "",
    "gold": ""
  }
}
```

## Mixed Format (CommonMeta)

**Input:**

```
useruuid=f3147754-7646-4687-8804-7acdf233c159;return=kcglkiavqq;username=jak7b;free money go
```

**Output:**

```json
{
  "version": 0,
  "isFallback": true,
  "entries": [
    { "name": "useruuid", "value": "f3147754-7646-4687-8804-7acdf233c159" },
    { "name": "return", "value": "kcglkiavqq" },
    { "name": "username", "value": "jak7b" },
    { "name": "free money go", "value": "" }
  ],
  "data": {
    "useruuid": "f3147754-7646-4687-8804-7acdf233c159",
    "return": "kcglkiavqq",
    "username": "jak7b",
    "free money go": ""
  }
}
```
