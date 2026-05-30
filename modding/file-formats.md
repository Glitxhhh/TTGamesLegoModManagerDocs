---
title: File Formats
parent: For Mod Authors
nav_order: 7
---

# File Formats
{: .no_toc }

Reference for TT Games file formats you'll encounter when modding.

---

## Archives

| Format | Extension | Purpose | Tool |
|---|---|---|---|
| DAT archive | `.DAT` | Main game data container — all assets packed in | QuickBMS + `ttgames.bms` |
| DATWIN archive | `.DATWIN` | HP Collection variant of DAT | QuickBMS + `lego_hp_collection_datwin.bms` |
| CBX | `.CBX` | Compressed audio (Chatterbox — EA MicroTalk codec variant) | CBXDecoder → WAV |

---

## Models & Scenes

| Format | Extension | Purpose | Notes |
|---|---|---|---|
| GSC/GHG/FNT | `.GSC` `.GHG` `.FNT` | Model and texture container | GHG = character/vehicle models with skeleton; must be in `CHARS/` for Nu2 PS2-HD |
| NUP | `.NUP` | Nu2 PS2 sub-engine format | LSW1, LSW2 only |

**Tool:** Noesis + community scripts for viewing; LEGO Star Wars PLY Model Importer for new models.

---

## Audio

| Format | Extension | Purpose |
|---|---|---|
| WAV | `.WAV` | Uncompressed sound effects |
| ADP | `.ADP` | ADPCM-compressed audio (later games) |
| WGT | `.WGT` | Music (decompressed from OGG at install time, early games) |
| CBX | `.CBX` | Compressed voice lines (Chatterbox format) |

**Encoding ADP:** `ffmpeg -i input.wav -f wav -acodec adpcm_ms output.ADP`

---

## Character Data

| Format | Extension | Purpose | Games |
|---|---|---|---|
| Character Definition | `.CD` | Binary character asset reference (replaced plain .TXT) | LIJ2 onwards |
| APJ | `.APJ` | Binary character list (replaced CHARS.TXT) | NXG Creator onwards |
| CHARS.TXT | `.TXT` | Plain-text character registration | LB1 and earlier |

---

## Video

| Format | Extension | Purpose |
|---|---|---|
| Bink | `.BIK` | Pre-rendered video (older titles — LB1, LIJ1 DS) |
| FMV | `.FMV` | Pre-rendered video (LCU PC, Worlds, TLMV2 PC, others) |

---

## Textures

| Format | Extension | Purpose | Notes |
|---|---|---|---|
| TSH / NuTextureSheet | `.TSH` | Texture container | v4 from LB3, v5 nearly identical, v11 in Skywalker Saga |
| DDS | `.DDS` | DirectX texture (embedded in GSC/GHG) | Up to 4096×4096 in DX9 titles |

**Tool:** NUTCrackerV3 for NXG texture extraction/repacking.

---

## Text & Localisation

| Format | Extension | Purpose | Location |
|---|---|---|---|
| COLLECTION.TXT | `.TXT` | Character/vehicle unlock conditions | `CHARS/` |
| CHARS.TXT | `.TXT` | Character registration (Nu2 era) | `CHARS/` |
| Cornwall CSV | `.CSV` | Multilingual in-game text | `STUFF/TEXT/TEXT.CSV` (LSW3+) or `TRC.CSV` (TCS/LIJ1/LB1) |
| GIZ / Gizmo | `.GIZ` | Interactive level objects (levers, studs, buildables) | Level directories |

---

## Tools Summary

| Tool | Purpose | Where |
|---|---|---|
| QuickBMS + ttgames.bms | Extract DAT archives | [github.com/linterniGamer/Tt-Games-quickbms-scripts](https://github.com/linterniGamer/Tt-Games-quickbms-scripts) |
| TTGamesPatcher | Patch exe for TFA/NTT games | [github.com/AlubJ/TTGamesPatcher](https://github.com/AlubJ/TTGamesPatcher) |
| TTGames Explorer Rebirth | Browse/extract game archives | Community Discord |
| NUTCrackerV3 | NXG texture extraction/repack | Community Discord |
| CBXDecoder | Convert CBX audio to WAV | Community Discord |
| Noesis | View GHG models | [richwhitehouse.com/index.php?content=inc_projects.php](https://richwhitehouse.com/index.php?content=inc_projects.php) |

---

## Further Reading

- [ttmodding.com](https://ttmodding.com) — community documentation
- [ttmodding.fandom.com](https://ttmodding.fandom.com) — wiki with file format details and character lists
