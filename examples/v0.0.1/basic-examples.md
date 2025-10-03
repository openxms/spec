# Basic XMS v0.0.1 Examples

## Simple User Transaction

**Input:**

```
xms/1;username=steve;useruuid=550e8400e29b41d4a716446655440000;return=k123456789
```

**Output:**

```json
{
  "version": 1,
  "isFallback": false,
  "entries": [
    { "name": "username", "value": "steve" },
    { "name": "useruuid", "value": "550e8400e29b41d4a716446655440000" },
    { "name": "return", "value": "k123456789" }
  ],
  "data": {
    "username": "steve",
    "useruuid": "550e8400e29b41d4a716446655440000",
    "return": "k123456789"
  }
}
```

## Item Purchase with Message

**Input:**

```
xms/1;username=HerrKatzeGaming;useruuid=1f558cbb-0752-49c0-ace4-7f9ed0506fe3;item="diamond_sword";message="We're no strangers to love";return=keqlk54hx2
```

**Output:**

```json
{
  "version": 1,
  "isFallback": false,
  "entries": [
    { "name": "username", "value": "HerrKatzeGaming" },
    { "name": "useruuid", "value": "1f558cbb-0752-49c0-ace4-7f9ed0506fe3" },
    { "name": "item", "value": "diamond_sword" },
    { "name": "message", "value": "We're no strangers to love" },
    { "name": "return", "value": "keqlk54hx2" }
  ],
  "data": {
    "username": "HerrKatzeGaming",
    "useruuid": "1f558cbb-0752-49c0-ace4-7f9ed0506fe3",
    "item": "diamond_sword",
    "message": "We're no strangers to love",
    "return": "keqlk54hx2"
  }
}
```

## Error Response

**Input:**

```
xms/1;error.code=404;error.message="You must supply a valid product to purchase!"
```

**Output:**

```json
{
  "version": 1,
  "isFallback": false,
  "entries": [
    { "name": "error.code", "value": "404" },
    {
      "name": "error.message",
      "value": "You must supply a valid product to purchase!"
    }
  ],
  "data": {
    "error": {
      "code": "404",
      "message": "You must supply a valid product to purchase!"
    },
    "error.code": "404",
    "error.message": "You must supply a valid product to purchase!"
  }
}
```

## Nested User Information

**Input:**

```
xms/1;username=steve;useruuid=550e8400;user.stats.level=25;user.stats.coins=1000
```

**Output:**

```json
{
  "version": 1,
  "isFallback": false,
  "entries": [
    { "name": "username", "value": "steve" },
    { "name": "useruuid", "value": "550e8400" },
    { "name": "user.stats.level", "value": "25" },
    { "name": "user.stats.coins", "value": "1000" }
  ],
  "data": {
    "user": {
      "stats": {
        "level": "25",
        "coins": "1000"
      }
    },
    "username": "steve",
    "useruuid": "550e8400",
    "user.stats.level": "25",
    "user.stats.coins": "1000"
  }
}
```

## Empty and Null Values

**Input:**

```
xms/1;username=steve;message="";description=;notes
```

**Output:**

```json
{
  "version": 1,
  "isFallback": false,
  "entries": [
    { "name": "username", "value": "steve" },
    { "name": "message", "value": "" },
    { "name": "description", "value": null },
    { "name": "notes", "value": null }
  ],
  "data": {
    "username": "steve",
    "message": "",
    "description": null,
    "notes": null
  }
}
```
