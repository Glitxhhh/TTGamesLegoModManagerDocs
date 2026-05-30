---
title: Game IDs Reference
parent: For Mod Authors
nav_order: 4
---

# Game IDs Reference
{: .no_toc }

Use the **Short ID** in your `mod.json`'s `"game"` field, and as folder/file names when organizing your mod.

---

## All Supported Games

| # | Short ID | Full Name | Engine | Notes |
|---|---|---|---|---|
| 1 | `lsw-tcs` | LEGO Star Wars: The Complete Saga | Nu2 (PS2-HD) | "Holy trinity" — GHG/GSC files |
| 2 | `lij1` | LEGO Indiana Jones: The Original Adventures | Nu2 (PS2-HD) | |
| 3 | `lb1` | LEGO Batman: The Videogame | Nu2 (PS2-HD) | CHARS.TXT block format |
| 4 | `lij2` | LEGO Indiana Jones 2: The Adventure Continues | NXG / Creator | Uses .CD and .APJ files |
| 5 | `lhp1` | LEGO Harry Potter: Years 1-4 | NXG / Creator | |
| 6 | `lswiii` | LEGO Star Wars III: The Clone Wars | NXG / Builder | |
| 7 | `lpotc` | LEGO Pirates of the Caribbean: The Video Game | NXG / Builder | Delisted — key resellers only |
| 8 | `lhp2` | LEGO Harry Potter: Years 5-7 | NXG / Builder | |
| 9 | `lb2` | LEGO Batman 2: DC Super Heroes | NXG / Gotham | |
| 10 | `llotr` | LEGO The Lord of the Rings | NXG / Gotham | Delisted — key resellers only |
| 11 | `lcu` | LEGO City Undercover | NXG / Cinema DX11 | PC port (2017) |
| 12 | `lms1` | LEGO Marvel Super Heroes | NXG / Cinema DX9 | |
| 13 | `llego-movie` | The LEGO Movie Videogame | NXG / Cinema DX9 | |
| 14 | `lhobbit` | LEGO The Hobbit | NXG / Cinema DX9 | Delisted — key resellers only |
| 15 | `lb3` | LEGO Batman 3: Beyond Gotham | NXG / Cinema DX9+DX11 | |
| 16 | `ljw` | LEGO Jurassic World | NXG / Cinema DX9+DX11 | |
| 17 | `ldimensions` | LEGO Dimensions | NXG / Cinema | Console only — emulator support planned |
| 18 | `lma` | LEGO Marvel's Avengers | NXG / TFA DX9+DX11 | Requires patched exe |
| 19 | `lswfa` | LEGO Star Wars: The Force Awakens | NXG / TFA DX9+DX11 | Requires patched exe |
| 20 | `lworlds` | LEGO Worlds | NXG / TFA | Requires patched exe |
| 21 | `lninjago-movie` | The LEGO Ninjago Movie Video Game | NXG / TFA DX11 | Requires patched exe |
| 22 | `lms2` | LEGO Marvel Super Heroes 2 | NXG / TFA DX11 | Requires patched exe |
| 23 | `linc` | LEGO The Incredibles | NXG / TFA DX11 | Requires patched exe |
| 24 | `ldc-sv` | LEGO DC Super-Villains | NXG / TFA DX11 | Requires patched exe |
| 25 | `llego-movie2` | The LEGO Movie 2 Videogame | NXG / TFA DX11 | Requires patched exe |
| 26 | `lsw-skywalker` | LEGO Star Wars: The Skywalker Saga | NTT | DAT-based; requires patched exe |
| 27 | `lhp-collection` | LEGO Harry Potter Collection | NXG / TFA DX11 | Uses `.datwin` archives |
| 28 | `lb-legacy` | LEGO Batman: Legacy of the Dark Knight | Unreal Engine 5 | Pak/ue4ss support planned |

---

## Engine Groups

Knowing the engine helps you understand which files to mod and which tools to use.

### Nu2 PS2-HD (TCS, LIJ1, LB1)
- Character models: `.GHG` files in `chars/<name>/`
- Scenes: `.GSC` files
- Character list: `CHARS/COLLECTION.TXT` (plain text, one `collect` entry per line)
- Character registration: `CHARS/CHARS.TXT` (`char_start` / `dir` / `file` / `char_end` blocks)

### NXG Creator (LIJ2, LHP1)
- Replaced `CHARS.TXT` with binary `.APJ` files
- Character definitions: binary `.CD` files
- New character archive format: `.CBX`

### NXG Builder / Gotham / Cinema / TFA
- Similar to Creator but with evolving formats
- TFA variant games require a **patched executable** to load modded files

### NTT (Skywalker Saga)
- Still uses DAT archives (same extraction process)
- Requires patched executable
- Different internal file structure — modding tools are still maturing

---

## Notes on Delisted Games

LEGO Lord of the Rings, LEGO The Hobbit, and LEGO Pirates of the Caribbean are no longer on Steam due to expired licences, but can be purchased via key resellers and are fully supported by the manager.
