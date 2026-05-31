---
title: Game IDs Reference
parent: For Mod Authors
nav_order: 4
---

# Game IDs Reference
{: .no_toc }

Use the **Short ID** in your `mod.json`'s `"game"` field.

---

## All Supported Games

| # | Short ID | Full Name | Engine |
|---|---|---|---|
| 1 | `lsw-tcs` | LEGO Star Wars: The Complete Saga | Nu2 (PS2-HD) |
| 2 | `lij1` | LEGO Indiana Jones: The Original Adventures | Nu2 (PS2-HD) |
| 3 | `lb1` | LEGO Batman: The Videogame | Nu2 (PS2-HD) |
| 4 | `lij2` | LEGO Indiana Jones 2: The Adventure Continues | NXG / Creator |
| 5 | `lhp1` | LEGO Harry Potter: Years 1-4 | NXG / Creator |
| 6 | `lswiii` | LEGO Star Wars III: The Clone Wars | NXG / Builder |
| 7 | `lpotc` | LEGO Pirates of the Caribbean: The Video Game | NXG / Builder |
| 8 | `lhp2` | LEGO Harry Potter: Years 5-7 | NXG / Builder |
| 9 | `lb2` | LEGO Batman 2: DC Super Heroes | NXG / Gotham |
| 10 | `llotr` | LEGO The Lord of the Rings | NXG / Gotham |
| 11 | `lcu` | LEGO City Undercover | NXG / Cinema DX11 |
| 12 | `lms1` | LEGO Marvel Super Heroes | NXG / Cinema DX9 |
| 13 | `llego-movie` | The LEGO Movie Videogame | NXG / Cinema DX9 |
| 14 | `lhobbit` | LEGO The Hobbit | NXG / Cinema DX9 |
| 15 | `lb3` | LEGO Batman 3: Beyond Gotham | NXG / Cinema DX9+DX11 |
| 16 | `ljw` | LEGO Jurassic World | NXG / Cinema DX9+DX11 |
| 17 | `ldimensions` | LEGO Dimensions | NXG / Cinema |
| 18 | `lma` | LEGO Marvel's Avengers | NXG / TFA DX9+DX11 |
| 19 | `lswfa` | LEGO Star Wars: The Force Awakens | NXG / TFA DX9+DX11 |
| 20 | `lworlds` | LEGO Worlds | NXG / TFA |
| 21 | `lninjago-movie` | The LEGO Ninjago Movie Video Game | NXG / TFA DX11 |
| 22 | `lms2` | LEGO Marvel Super Heroes 2 | NXG / TFA DX11 |
| 23 | `linc` | LEGO The Incredibles | NXG / TFA DX11 |
| 24 | `ldc-sv` | LEGO DC Super-Villains | NXG / TFA DX11 |
| 25 | `llego-movie2` | The LEGO Movie 2 Videogame | NXG / TFA DX11 |
| 26 | `lsw-skywalker` | LEGO Star Wars: The Skywalker Saga | NTT |
| 27 | `lhp-collection` | LEGO Harry Potter Collection | NXG / TFA DX11 |
| 28 | `lb-legacy` | LEGO Batman: Legacy of the Dark Knight | Unreal Engine 5 |

---

## Engine Groups

### Nu2 (PS2-HD) — TCS, LIJ1, LB1
Classic era. Character models use `.GHG` files. Character list in `CHARS/CHARS.TXT` (block format).

### NXG — LIJ2 through TLMV2, Worlds
All NXG variants share the same extraction and merge pipeline. TFA variant games require a patched executable after extraction.

### NTT — The Skywalker Saga
Uses DAT archives like NXG. Requires TTGamesPatcher after extraction.

### Unreal Engine 5 — Legacy of the Dark Knight
Pak mods (`.pak/.ucas/.utoc`) and UE4SS script/blueprint mods. No DAT extraction needed.
UE4SS required for script mods: [nexusmods.com/legobatmanlegacyofthedarkknight/mods/5](https://www.nexusmods.com/legobatmanlegacyofthedarkknight/mods/5)
