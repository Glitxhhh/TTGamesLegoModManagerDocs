---
title: mod.json Reference
parent: For Mod Authors
nav_order: 3
---

# mod.json Reference
{: .no_toc }

Place `mod.json` in the **root** of your mod folder (alongside `files/`). All fields are optional but recommended.

---

## Full Example

```json
{
    "name": "Dark Knight Batman Skin",
    "author": "YourName",
    "version": "1.2.0",
    "description": "Replaces Batman's model and adds two new villain characters.",
    "game": "lb1",
    "minimumManagerVersion": "1.0.0",
    "tags": ["characters", "reskin"],
    "url": "https://gamebanana.com/mods/your-mod-page"
}
```

---

## Fields

| Field | Type | Description |
|---|---|---|
| `name` | string | Display name shown in the mod list |
| `author` | string | Your name or username |
| `version` | string | Semantic version, e.g. `"1.0.0"` |
| `description` | string | Short description of what the mod does |
| `game` | string | Short ID of the target game (see [Game IDs](game-ids)). Optional — mod works for any game if omitted |
| `minimumManagerVersion` | string | Minimum manager version required (optional) |
| `tags` | array | Keywords for discovery, e.g. `["characters", "audio", "levels"]` |
| `url` | string | Link to mod page on GameBanana, NexusMods, etc. |

---

## The `game` field

Use the **Short ID** from the [Game IDs](game-ids) page. Examples:

```json
"game": "lb1"       // LEGO Batman: The Videogame
"game": "lms1"      // LEGO Marvel Super Heroes
"game": "lsw-tcs"   // LEGO Star Wars: The Complete Saga
```

If your mod works with multiple games, omit this field — users install it against whichever game they choose in the manager.

---

## Example mod.json Files

**Simple character replacement:**
```json
{
    "name": "Movie Batman Skin",
    "author": "CoolModder",
    "version": "1.0.0",
    "game": "lb1"
}
```

**New character with cheat code:**
```json
{
    "name": "Bane Classic",
    "author": "CoolModder",
    "version": "1.1.0",
    "description": "Adds classic Bane from the comics as a purchasable character.",
    "game": "lb1",
    "tags": ["characters", "new-character"]
}
```

**Audio replacement:**
```json
{
    "name": "Batman 1989 Soundtrack",
    "author": "AudioModder",
    "version": "2.0.0",
    "description": "Replaces the main hub music with tracks from the 1989 Tim Burton film.",
    "game": "lb1",
    "tags": ["audio", "music"]
}
```
