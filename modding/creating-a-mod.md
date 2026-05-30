---
title: Creating a Mod
parent: For Mod Authors
nav_order: 1
---

# Creating a Mod
{: .no_toc }

## Quick Start

1. Create a folder for your mod
2. Add a `mod.json` with your mod's metadata
3. Create a `files/` subfolder mirroring the game's extracted directory structure
4. Add only the files you want to change or add
5. For character additions, add **only your new entries** to `CHARS/COLLECTION.TXT` — the manager merges it automatically
6. Zip your folder and distribute

---

## Minimal Example

```
my-batman-skin/
├── mod.json
└── files/
    └── chars/
        └── batman/
            └── batman.ghg        ← replacement character model
```

**`mod.json`:**
```json
{
    "name": "Dark Knight Batman Skin",
    "author": "YourName",
    "version": "1.0.0",
    "description": "Replaces Batman's model with a darker, more movie-accurate version.",
    "game": "lb1"
}
```

---

## Adding a New Character

When adding a brand-new character (not replacing an existing one), you also need to register it in `COLLECTION.TXT` so the game can unlock it:

```
my-new-character-mod/
├── mod.json
└── files/
    ├── CHARS/
    │   └── COLLECTION.TXT        ← ONLY your new collect entries
    └── chars/
        └── mynewchar/
            ├── mynewchar.ghg     ← character model
            └── mynewchar.NUP     ← (if applicable)
```

**`CHARS/COLLECTION.TXT`** — only include the lines YOUR mod adds:
```
collect "mynewchar" buy_in_shop 10000 cheat_code "ABC123"
```

The manager reads this file, extracts only the entries that don't already exist in the game's original `COLLECTION.TXT`, and merges them in automatically. You do **not** need to copy the entire original file.

---

## Distributing as a Zip

Zip your mod folder directly. The manager handles both:

```
# Flat zip (folder is the mod root):
my-mod.zip
└── files/
    └── ...

# Wrapped zip (single top-level folder, auto-unwrapped):
my-mod.zip
└── my-mod/
    ├── mod.json
    └── files/
        └── ...
```

Both structures work. The manager descends into a single top-level folder automatically.

> **Tip:** Including a `mod.json` makes your mod show author/version info in the manager's mod list. Without it the mod still installs fine, using the zip's filename as the display name.
