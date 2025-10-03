# Array Examples - XMS v0.0.1

## Simple Item Array

**Input:**

```
xms/1;items.0=sword;items.1=shield;items.2=potion;count=3
```

**Output:**

```json
{
  "version": 1,
  "isFallback": false,
  "entries": [
    { "name": "items.0", "value": "sword" },
    { "name": "items.1", "value": "shield" },
    { "name": "items.2", "value": "potion" },
    { "name": "count", "value": "3" }
  ],
  "data": {
    "items": ["sword", "shield", "potion"],
    "count": "3"
  }
}
```

## Multi-dimensional Array

**Input:**

```
xms/1;grid.0.0=A1;grid.0.1=A2;grid.1.0=B1;grid.1.1=B2
```

**Output:**

```json
{
  "version": 1,
  "isFallback": false,
  "entries": [
    { "name": "grid.0.0", "value": "A1" },
    { "name": "grid.0.1", "value": "A2" },
    { "name": "grid.1.0", "value": "B1" },
    { "name": "grid.1.1", "value": "B2" }
  ],
  "data": {
    "grid": [
      ["A1", "A2"],
      ["B1", "B2"]
    ]
  }
}
```

## Mixed Array with Objects

**Input:**

```
xms/1;users.0.name=alice;users.0.level=10;users.1.name=bob;users.1.level=15;total=2
```

**Output:**

```json
{
  "version": 1,
  "isFallback": false,
  "entries": [
    { "name": "users.0.name", "value": "alice" },
    { "name": "users.0.level", "value": "10" },
    { "name": "users.1.name", "value": "bob" },
    { "name": "users.1.level", "value": "15" },
    { "name": "total", "value": "2" }
  ],
  "data": {
    "users": [
      { "name": "alice", "level": "10" },
      { "name": "bob", "level": "15" }
    ],
    "total": "2"
  }
}
```

## Sparse Array

**Input:**

```
xms/1;items.0=sword;items.5=bow;items.10=arrow
```

**Output:**

```json
{
  "version": 1,
  "isFallback": false,
  "entries": [
    { "name": "items.0", "value": "sword" },
    { "name": "items.5", "value": "bow" },
    { "name": "items.10", "value": "arrow" }
  ],
  "data": {
    "items": [
      "sword",
      null,
      null,
      null,
      null,
      "bow",
      null,
      null,
      null,
      null,
      "arrow"
    ]
  }
}
```
