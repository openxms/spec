# Real-World Examples - XMS v0.0.1

Based on actual transaction metadata from the kromer ecosystem.

## Gaming Transaction

**Input:**

```
useruuid=1f558cbb-0752-49c0-ace4-7f9ed0506fe3;return=keqlk54hx2;username=HerrKatzeGaming;message=We're no strangers to love
```

**Parsed as CommonMeta (v0):**

```json
{
  "version": 0,
  "isFallback": true,
  "entries": [
    { "name": "useruuid", "value": "1f558cbb-0752-49c0-ace4-7f9ed0506fe3" },
    { "name": "return", "value": "keqlk54hx2" },
    { "name": "username", "value": "HerrKatzeGaming" },
    { "name": "message", "value": "We're no strangers to love" }
  ],
  "data": {
    "useruuid": "1f558cbb-0752-49c0-ace4-7f9ed0506fe3",
    "return": "keqlk54hx2",
    "username": "HerrKatzeGaming",
    "message": "We're no strangers to love"
  }
}
```

## KromerFlip Game Result

**Input:**

```
KF#226;winner=not_Drake_O;loser=Drake_o;roll=1
```

**Parsed as CommonMeta (v0):**

```json
{
  "version": 0,
  "isFallback": true,
  "entries": [
    { "name": "KF#226", "value": "" },
    { "name": "winner", "value": "not_Drake_O" },
    { "name": "loser", "value": "Drake_o" },
    { "name": "roll", "value": "1" }
  ],
  "data": {
    "KF#226": "",
    "winner": "not_Drake_O",
    "loser": "Drake_o",
    "roll": "1"
  }
}
```

## Bingo Game Payout

**Input:**

```
KB#71;winner_ticket=8;winner=Hellscaped;payout=75
```

**Parsed as CommonMeta (v0):**

```json
{
  "version": 0,
  "isFallback": true,
  "entries": [
    { "name": "KB#71", "value": "" },
    { "name": "winner_ticket", "value": "8" },
    { "name": "winner", "value": "Hellscaped" },
    { "name": "payout", "value": "75" }
  ],
  "data": {
    "KB#71": "",
    "winner_ticket": "8",
    "winner": "Hellscaped",
    "payout": "75"
  }
}
```

## Shop Transaction with Owner Info

**Input:**

```
owner=hartbreix;
```

**Parsed as CommonMeta (v0):**

```json
{
  "version": 0,
  "isFallback": true,
  "entries": [{ "name": "owner", "value": "hartbreix" }],
  "data": {
    "owner": "hartbreix"
  }
}
```

## System Messages

**Input:**

```
message=Here is the funds remaining after your purchase!
```

**Parsed as CommonMeta (v0):**

```json
{
  "version": 0,
  "isFallback": true,
  "entries": [
    {
      "name": "message",
      "value": "Here is the funds remaining after your purchase!"
    }
  ],
  "data": {
    "message": "Here is the funds remaining after your purchase!"
  }
}
```

## Modern XMS v1 Equivalent

Here's how some of these would look using proper XMS v1 format:

**Gaming Transaction (XMS v1):**

```
xms/1;useruuid=1f558cbb-0752-49c0-ace4-7f9ed0506fe3;return=keqlk54hx2;username=HerrKatzeGaming;message="We're no strangers to love"
```

**Game Result (XMS v1):**

```
xms/1;game.type=kromerflip;game.id=226;winner=not_Drake_O;loser=Drake_o;roll=1
```

**Shop Transaction (XMS v1):**

```
xms/1;owner.name=hartbreix;owner.return=key20a326w;shop=main
```
