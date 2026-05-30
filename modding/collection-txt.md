---
title: COLLECTION.TXT Guide
parent: For Mod Authors
nav_order: 5
---

# COLLECTION.TXT Guide
{: .no_toc }

`COLLECTION.TXT` (located at `CHARS/collection.txt` inside the extracted game) defines which characters and vehicles can be unlocked in the game — how they're obtained, their shop price, and their cheat code.

It exists in **every game from TCS through TLMV2** and is the primary file to edit when adding new characters.

---

## File Location

```
<game install dir>/
└── CHARS/
    └── COLLECTION.TXT      ← edit this
```

---

## Format

Each unlockable character gets one line:

```
collect "character_id" [unlock_conditions...]
```

### Unlock conditions (combine as many as needed)

| Keyword | Description | Example |
|---|---|---|
| *(none)* | Available from the start (hardcoded) | `collect "batman"` |
| `story` | Unlocked after completing a story mission | `story` |
| `area_complete "level_id"` | Unlocked after finishing a specific level | `area_complete "7BatCave"` |
| `buy_in_shop N` | Can be purchased for N studs | `buy_in_shop 125000` |
| `cheat_code "CODE"` | Unlockable via cheat code | `cheat_code "JKR331"` |
| `any_hero_episode_complete` | After completing any hero episode (LB1) | |
| `all_hero_episodes_complete` | After all hero episodes complete (LB1) | |
| `all_episodes_complete` | After all main episodes (TCS) | |
| `minikit` | After collecting all minikits in a stage | |
| `100_percent` | After 100% completion | |
| `supercounter_complete` | After rescuing all hostages (LB1) | |

---

## Examples

**Standard purchasable character with cheat code:**
```
collect "brucewayne" area_complete "gothamcity1" buy_in_shop 100000 cheat_code "BDJ327"
```

**Available from the start:**
```
collect "batman" // available from the start!
```

**Story unlock + shop:**
```
collect "superman" story customiser_parts
```

**Shop only:**
```
collect "aquaman" buy_in_shop 125000
```

---

## Adding Your Character

Include **only the new lines your mod adds** in your mod's `CHARS/COLLECTION.TXT`. The manager automatically merges them with the original file.

**Do not copy the entire original file** — the manager reads the original from the game directory and only appends unique entries from your mod.

Example — your mod file `CHARS/COLLECTION.TXT`:
```
;--- My Mod Characters ---
collect "mynewchar" buy_in_shop 10000 cheat_code "ABC123"
collect "mynewvehicle" minikit
```

The manager will:
1. Read the game's original `COLLECTION.TXT`
2. Check each line in your file against the original
3. Deduplication is by **character ID** (the first quoted token after `collect`) — if the same ID already exists (even with different conditions), your line is skipped
4. Append only the genuinely new entries

---

## Comment Syntax

Lines starting with `;`, `//`, or `#` are treated as comments and ignored:

```
;-----------------------;
; MY MOD CHARACTERS     ;
;-----------------------;
collect "mynewchar" buy_in_shop 10000
```

---

## CHARS.TXT (LB1 / Nu2 only)

LEGO Batman: The Videogame uses a separate `CHARS.TXT` file that **registers** characters with the engine. This uses a block format:

```
char_start
    dir "mynewchar"
    file "mynewchar"
char_end
```

Include **only blocks for your new characters**. The manager merges by character ID (`dir "..."`) at the block level — it won't add a duplicate block if that character ID already exists.

**Path:** `CHARS/CHARS.TXT`
