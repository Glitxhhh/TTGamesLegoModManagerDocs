<div align="center">
  <img src="resources/icons/app.png" width="100" alt="TTGames Lego Mod Manager">

  # TTGames Lego Mod Manager

  A mod manager for TT Games LEGO titles — install, enable and combine mods without manually editing game files.

  [![Version](https://img.shields.io/badge/version-1.0.0--dev-blue)](https://github.com/Glitxhhh/TTGamesLegoModManagerDocs/releases)
  [![Platform](https://img.shields.io/badge/platform-Windows-lightgrey)](#)
  [![Engines](https://img.shields.io/badge/engines-Nu2%20%7C%20NXG%20%7C%20NTT-orange)](#supported-games)
  [![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

  [**Download**](https://github.com/Glitxhhh/TTGamesLegoModManagerDocs/releases) &nbsp;·&nbsp;
  [**Modding Guide**](https://glitxhhh.github.io/TTGamesLegoModManagerDocs/modding) &nbsp;·&nbsp;
  [**Game IDs**](https://glitxhhh.github.io/TTGamesLegoModManagerDocs/modding/game-ids)
</div>

---

## Features

### For Players
- **Auto-detect games** via Steam library scanning (Windows + Linux)
- **One-click DAT extraction** — QuickBMS tools downloaded automatically
- **Enable/disable mods** without redownloading or repacking anything
- **Deploy preview** — see exactly what changes before committing
- **Restore Vanilla** — undo all mods and restore original files instantly
- **Conflict detection** — real-time warnings when mods touch the same file

### For Mod Compatibility
- **Automatic file merging** — `COLLECTION.TXT`, `AUDIO.CFG`, `LEVELS.TXT` and more are merged intelligently so multiple mods can coexist
- **Deduplication by character ID** — two mods adding the same character won't conflict
- **Priority ordering** — drag to reorder mods; top of list wins conflicts
- **Zip/RAR/7z support** — install mods from any archive format; nested folders auto-detected

### Technical
- **Single portable exe** — no installer, no DLLs, drop it anywhere
- **Stable AppData path** — data survives app renames and updates
- **Steam capsule art** embedded for all 27+ supported titles
- **TTGamesPatcher integration** — one-click exe patching for TFA variant games

---

## Supported Games

28 titles across Nu2 (PS2-HD), NXG (Creator / Builder / Gotham / Cinema / TFA), and NTT engines.

<details>
<summary>Full game list (click to expand)</summary>

| Short ID | Game | Engine |
|---|---|---|
| `lsw-tcs` | LEGO Star Wars: The Complete Saga | Nu2 (PS2-HD) |
| `lij1` | LEGO Indiana Jones: The Original Adventures | Nu2 (PS2-HD) |
| `lb1` | LEGO Batman: The Videogame | Nu2 (PS2-HD) |
| `lij2` | LEGO Indiana Jones 2: The Adventure Continues | NXG / Creator |
| `lhp1` | LEGO Harry Potter: Years 1-4 | NXG / Creator |
| `lswiii` | LEGO Star Wars III: The Clone Wars | NXG / Builder |
| `lpotc` | LEGO Pirates of the Caribbean: The Video Game | NXG / Builder |
| `lhp2` | LEGO Harry Potter: Years 5-7 | NXG / Builder |
| `lb2` | LEGO Batman 2: DC Super Heroes | NXG / Gotham |
| `llotr` | LEGO The Lord of the Rings | NXG / Gotham |
| `lcu` | LEGO City Undercover | NXG / Cinema DX11 |
| `lms1` | LEGO Marvel Super Heroes | NXG / Cinema DX9 |
| `llego-movie` | The LEGO Movie Videogame | NXG / Cinema DX9 |
| `lhobbit` | LEGO The Hobbit | NXG / Cinema DX9 |
| `lb3` | LEGO Batman 3: Beyond Gotham | NXG / Cinema DX9+DX11 |
| `ljw` | LEGO Jurassic World | NXG / Cinema DX9+DX11 |
| `ldimensions` | LEGO Dimensions | NXG / Cinema |
| `lma` | LEGO Marvel's Avengers | NXG / TFA DX9+DX11 |
| `lswfa` | LEGO Star Wars: The Force Awakens | NXG / TFA DX9+DX11 |
| `lworlds` | LEGO Worlds | NXG / TFA |
| `lninjago-movie` | The LEGO Ninjago Movie Video Game | NXG / TFA DX11 |
| `lms2` | LEGO Marvel Super Heroes 2 | NXG / TFA DX11 |
| `linc` | LEGO The Incredibles | NXG / TFA DX11 |
| `ldc-sv` | LEGO DC Super-Villains | NXG / TFA DX11 |
| `llego-movie2` | The LEGO Movie 2 Videogame | NXG / TFA DX11 |
| `lsw-skywalker` | LEGO Star Wars: The Skywalker Saga | NTT |
| `lhp-collection` | LEGO Harry Potter Collection | NXG / TFA DX11 |
| `lb-legacy` | LEGO Batman: Legacy of the Dark Knight | Unreal Engine 5 |

</details>

---

## For Mod Authors

Full documentation is at **[glitxhhh.github.io/TTGamesLegoModManagerDocs](https://glitxhhh.github.io/TTGamesLegoModManagerDocs/modding)**.

Quick reference — a compatible mod looks like this:

```
my-mod.zip
├── mod.json
└── files/
    ├── CHARS/
    │   └── COLLECTION.TXT    ← only your NEW collect entries
    └── chars/
        └── mynewchar/
            └── mynewchar.ghg
```

**`mod.json`:**
```json
{
    "name": "My Mod Name",
    "author": "YourName",
    "version": "1.0.0",
    "description": "What this mod does.",
    "game": "lb2"
}
```

**`CHARS/COLLECTION.TXT`** — only include lines YOUR mod adds:
```
collect "mynewchar" buy_in_shop 10000 cheat_code "ABC123"
```

See the **[Mod Author Guide](https://glitxhhh.github.io/TTGamesLegoModManagerDocs/modding)** for the full `mod.json` spec, all game short IDs, COLLECTION.TXT format, mergeable files reference, and file format notes.

---

## Building from Source

```bat
:: Prerequisites: Qt 6.7+ (MSVC), CMake 3.20+, Visual Studio 2022

:: Development build (dynamic Qt, fast iteration)
build.bat run

:: Release build (static Qt, single standalone exe)
build.bat static clean
:: → TTGamesLegoModManager.exe in project root
```

Static Qt 6.10.1 must be built first — see `C:\Qt\build_static_qt.bat` or use the pre-built binaries from the releases page.

---

## Credits

By **[Glitxh](https://github.com/Glitxhhh)**

Modding documentation: [ttmodding.com](https://ttmodding.com) · [ttmodding.fandom.com](https://ttmodding.fandom.com)

QuickBMS scripts: [linterniGamer/Tt-Games-quickbms-scripts](https://github.com/linterniGamer/Tt-Games-quickbms-scripts)  
TTGamesPatcher: [AlubJ/TTGamesPatcher](https://github.com/AlubJ/TTGamesPatcher)
