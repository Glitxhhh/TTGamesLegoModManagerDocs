---
title: Mergeable Files
parent: For Mod Authors
nav_order: 6
---

# Mergeable Files
{: .no_toc }

These files are **automatically merged** by the manager when you deploy mods — you only need to include the entries your mod adds. Multiple mods can all contribute to the same file without conflict.

---

## How Merging Works

1. The manager reads the **original game file** as the base
2. For each enabled mod (in priority order), it reads that mod's version of the file
3. Only entries **not already present** in the base are added
4. The merged result is written to the game directory
5. The original is preserved in the manager's backup folder for `Restore Vanilla`

---

## Mergeable File List

| File | Location | Purpose | Notes |
|---|---|---|---|
| `COLLECTION.TXT` | `CHARS/` | Character/vehicle unlock conditions | Deduped by character ID (quoted token after `collect`) |
| `CHARS.TXT` | `CHARS/` | Character engine registration | Block-level merge (`char_start…char_end` by `dir "id"`) |
| `AUDIO.CFG` | `AUDIO/` | Audio asset registry | Line-level merge |
| `MUSIC.CFG` | `AUDIO/` | Music track list | Line-level merge |
| `CLIPS.TXT` | `CUT/` | Cutscene clip registry | Line-level merge |
| `CUTSCENES.TXT` | `CUT/` | Cutscene sequence list | Line-level merge |
| `AREAS.TXT` | `LEVELS/` | Area/hub definitions | Line-level merge |
| `EPISODES.TXT` | `LEVELS/` | Episode groupings | Line-level merge |
| `LEVELS.TXT` | `LEVELS/` | Level list | Line-level merge |
| `TEXT.CSV` | `STUFF/TEXT/` | Localisation — all languages (LSW3 onwards) | Cornwall CSV format |
| `TRC.CSV` | `STUFF/TEXT/` | Localisation — older format (TCS/LIJ1/LB1) | Cornwall CSV format |

---

## Line-Level Deduplication

For files other than `COLLECTION.TXT` and `CHARS.TXT`, deduplication works as follows:

1. **If the line contains a quoted string** (e.g. `"my_audio_track"`), the first quoted token is used as the key
2. **Otherwise**, the entire trimmed line (case-insensitive) is the key

This means two mods can add `"my_level"` entries with different parameters and only one will be included — the one from the **higher priority mod** (top of the mod list).

---

## Cornwall Localisation Files (TEXT.CSV / TRC.CSV)

These are CSV files that store all in-game text in multiple languages. Format:

```csv
"LABEL","PLATFORM","TYPE","ENGLISH","FRENCH","GERMAN","SPANISH",...
"MY_CHAR_NAME","All","Char","My Character","Mon Personnage","Mein Charakter","Mi Personaje",...
```

If your mod adds a new character, add a row for its display name. The manager merges by the `LABEL` column (first column).

**`TRC.CSV`** (TCS, LIJ1, LB1) has fewer columns — no `PLATFORM` or `TYPE`:
```csv
"LABEL","ENGLISH","FRENCH","GERMAN",...
```

---

## Non-Mergeable Files

All other files in your mod's `files/` folder are treated as **direct replacements**:
- The original is backed up on first deploy
- Your mod's version is copied to the game directory
- If two mods replace the same file, the **higher-priority mod** (top of list) wins
- The conflict is shown in the Deploy Preview before you commit

> **Tip:** Use mergeable files where possible — they allow multiple mods to coexist without conflicts.
