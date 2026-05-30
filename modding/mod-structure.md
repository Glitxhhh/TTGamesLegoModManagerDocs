---
title: Mod Structure
parent: For Mod Authors
nav_order: 2
---

# Mod Structure
{: .no_toc }

## Folder Layout

```
your-mod-name/
├── mod.json                    ← metadata (optional but recommended)
├── README.txt                  ← your readme (ignored by the manager — not copied to game)
└── files/                      ← mirrors the game's extracted directory structure
    ├── CHARS/
    │   ├── COLLECTION.TXT      ← only your NEW collect entries
    │   └── CHARS.TXT           ← only your NEW char_start blocks (LB1 only)
    ├── chars/
    │   └── mynewchar/
    │       └── mynewchar.ghg   ← character model
    ├── AUDIO/
    │   └── AUDIO.CFG           ← only your NEW audio entries
    ├── LEVELS/
    │   └── LEVELS.TXT          ← only your NEW level entries
    └── STUFF/
        └── TEXT/
            └── TEXT.CSV        ← only your NEW localisation rows
```

---

## Key Rules

### The `files/` folder is the game root
Everything inside `files/` mirrors the extracted game directory. A file at `files/chars/batman/batman.ghg` will be written to `<game>/chars/batman/batman.ghg`.

### Only include what you change
You do not need to copy unchanged files. The manager overlays your mod on top of the extracted game — unmodified files are untouched.

### For mergeable files, only include your additions
For `COLLECTION.TXT`, `AUDIO.CFG`, `LEVELS.TXT` etc., include **only the lines your mod adds**. The manager handles the merge automatically. See [Mergeable Files](mergeable-files) for the full list.

### Files to exclude (auto-ignored by the manager)
The following are automatically excluded during installation and will not be copied to the game directory:
- `*.txt`, `*.md`, `*.pdf`, `*.nfo`, `*.htm`, `*.html` — documentation
- `*.url`, `*.lnk` — shortcuts  
- `mod.json` — metadata (processed separately, not deployed)

---

## Zip / Archive Layout

When distributing as a zip, either structure works:

**Flat (recommended for simplicity):**
```
my-mod.zip
├── mod.json
└── files/
    └── ...
```

**Wrapped (single top-level folder — auto-detected):**
```
my-mod.zip
└── my-mod/
    ├── mod.json
    └── files/
        └── ...
```

The manager automatically descends into a single top-level folder if there are no loose files at the zip root, so both behave identically.

**Nested folders are NOT supported** (e.g. `my-mod.zip/subfolder1/subfolder2/files/`). Keep it to one level of wrapping at most.

---

## Path Case Sensitivity

Game file paths in extracted DATs use **UPPERCASE** for top-level folders (`CHARS/`, `AUDIO/`, `LEVELS/`) and **lowercase** for character-level subdirectories (`chars/batman/`). Match this exactly for best compatibility across platforms.

---

## Full Example — New Character Mod (LB2)

```
my-deadpool-mod/
├── mod.json
└── files/
    ├── CHARS/
    │   └── COLLECTION.TXT
    └── chars/
        └── deadpool/
            ├── deadpool.ghg
            ├── deadpool_icon.ghg
            └── deadpool_cape.ghg
```

**`mod.json`:**
```json
{
    "name": "Deadpool",
    "author": "YourName",
    "version": "1.0.0",
    "description": "Adds Deadpool as a purchasable character.",
    "game": "lb2"
}
```

**`CHARS/COLLECTION.TXT`:**
```
collect "deadpool" buy_in_shop 150000 cheat_code "DP4LYF"
```
