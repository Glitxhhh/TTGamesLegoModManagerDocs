<div align="center">

  # TTGames Lego Mod Manager

  A mod manager for TT Games LEGO titles.

  [![Version](https://img.shields.io/badge/version-1.0.0--beta-blue)](https://github.com/Glitxhhh/TTGamesLegoModManagerDocs/releases)
  [![Platform](https://img.shields.io/badge/platform-Windows-lightgrey)](#)
  [![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

  [**Download**](https://github.com/Glitxhhh/TTGamesLegoModManagerDocs/releases) &nbsp;·&nbsp;
  [**Modding Guide**](https://glitxhhh.github.io/TTGamesLegoModManagerDocs/modding) &nbsp;·&nbsp;
  [**Game IDs**](https://glitxhhh.github.io/TTGamesLegoModManagerDocs/modding/game-ids)
</div>

---

## Features

- **Auto-detect games** via Steam library
- **One-click DAT extraction** — tools downloaded automatically
- **Enable/disable mods** without touching original files
- **Smart file merging** — `COLLECTION.TXT`, `AUDIO.CFG`, `LEVELS.TXT` and more combined across mods automatically
- **Deploy preview** — see exactly what changes before applying
- **Restore Vanilla** — undo all mods instantly
- **Pak + UE4SS mod support** for Legacy of the Dark Knight
- Single portable exe — no installer, no DLLs needed

---

## Supported Games

28 titles from Nu2 through Unreal Engine 5, including:

- All classic Nu2 and NXG titles (Batman 1–3, Marvel, Indiana Jones, Harry Potter, Star Wars, Pirates, Lord of the Rings and more)
- **LEGO Star Wars: The Skywalker Saga** (NTT engine)
- **LEGO Worlds**
- **LEGO Batman: Legacy of the Dark Knight** (Unreal Engine 5 — pak + UE4SS mods)

[Full game list →](https://glitxhhh.github.io/TTGamesLegoModManagerDocs/modding/game-ids)

---

## For Mod Authors

Full guide at **[glitxhhh.github.io/TTGamesLegoModManagerDocs/modding](https://glitxhhh.github.io/TTGamesLegoModManagerDocs/modding)**

Quick format:

```
my-mod.zip
├── mod.json
└── files/
    ├── CHARS/
    │   └── COLLECTION.TXT    ← only your NEW entries
    └── chars/
        └── mynewchar/
            └── mynewchar.ghg
```

```json
{
    "name": "My Mod",
    "author": "YourName",
    "version": "1.0.0",
    "game": "lb2"
}
```

---

## Credits

By **[Glitxh](https://github.com/Glitxhhh)**

Modding docs: [ttmodding.com](https://ttmodding.com) · [ttmodding.fandom.com](https://ttmodding.fandom.com)  
QuickBMS scripts: [linterniGamer/Tt-Games-quickbms-scripts](https://github.com/linterniGamer/Tt-Games-quickbms-scripts)  
TTGamesPatcher: [AlubJ/TTGamesPatcher](https://github.com/AlubJ/TTGamesPatcher)
