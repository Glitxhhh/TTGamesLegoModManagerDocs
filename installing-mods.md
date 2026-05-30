---
title: Installing Mods
nav_order: 2
---

# Installing Mods
{: .no_toc }

## Prerequisites

1. Download `TTGamesLegoModManager.exe` from the [Releases](https://github.com/Glitxhhh/TTGamesLegoModManagerDocs/releases) page
2. Run it — no installer needed
3. Click **Scan for Games** to auto-detect your installed LEGO titles

## Workflow

### 1. Extract the game

Before mods can work, the game's DAT archives need to be extracted into the game folder.

Click **Extract** next to the game in the sidebar. Options:
- **Keep DATs** — leave original archives in place
- **Backup DATs** — move them to the manager's data folder (recommended)
- **Delete DATs** — remove them after extraction

> TFA variant games (Avengers, Force Awakens, Ninjago Movie, MSH2, Incredibles, DC Super-Villains, Movie 2) also require a **patched executable**. Click the orange **⚠ Patch Executable** button after extracting.

### 2. Install mods

Click **+ Add Mod** and select:
- A mod **folder** containing `files/` and optionally `mod.json`
- A **`.zip`**, **`.rar`**, or **`.7z`** archive

The manager automatically:
- Detects nested single-folder structure inside archives
- Ignores README, license, and documentation files
- Checks for conflicts with other installed mods

### 3. Enable and reorder

- Tick the checkbox to enable a mod
- Use **↑ ↓** to reorder — the **top of the list is highest priority** and wins conflicts

### 4. Apply to Game

Click **Apply to Game** to review:
- Which files are being added per mod
- Any file conflicts (shown in the Conflicts tab)
- What lines will be added to `COLLECTION.TXT` etc.

Then click **Deploy Mods** in the preview to write everything to the game folder.

### 5. Restore Vanilla

Click **Restore Vanilla** at any time to undo all mod changes and return to the original extracted files.

---

## Tips

- Use the **Open File ▾** dropdown to manually edit `COLLECTION.TXT`, `AUDIO.CFG` etc. in your default text editor for advanced conflict resolution
- The **Debug Console** (`Ctrl+\``) shows detailed logs of every operation
- Mods are stored in `%AppData%\TTGamesLegoModManager\mods\` and survive game updates
