---
title: Installing Mods
nav_order: 2
---

# Installing Mods
{: .no_toc }

## Get the manager

Download `TTGamesLegoModManager.exe` from the [Releases](https://github.com/Glitxhhh/TTGamesLegoModManagerDocs/releases) page. No installer — just run it.

---

## Step 1 — Add your game

Click **Scan for Games** to auto-detect installed Steam titles. If a game isn't found, use **+ Add Game** to point to its folder manually.

---

## Step 2 — Extract the game

Before mods work, the game's DAT archives need to be extracted. Click **Extract** next to the game in the sidebar and choose:

- **Extract + Backup DATs** *(recommended)* — moves the original DAT files to a safe backup location
- **Extract + Delete DATs** — removes the DATs after extraction to save space

> **TFA variant games** (Avengers, Force Awakens, Ninjago Movie, Marvel Super Heroes 2, Incredibles, DC Super-Villains, The LEGO Movie 2) and **The Skywalker Saga** also require clicking the orange **⚠ Patch Executable** button after extraction — this patches the game to load loose files correctly.

> **Legacy of the Dark Knight** (Unreal Engine 5) — no extraction needed. Mods deploy directly as pak files or UE4SS scripts.

---

## Step 3 — Install mods

Click **+ Add Mod** and select a mod folder or archive (`.zip`, `.rar`, `.7z`).

The manager automatically handles nested folder structures inside archives.

---

## Step 4 — Enable and order

- Tick the checkbox to enable a mod
- **Top of the list = highest priority** — use **↑ ↓** to reorder
- Right-click a mod to edit its name, author and version

---

## Step 5 — Apply to Game

Click **Apply to Game** to review what will change:

- The **Merges** tab shows what new entries will be added to `COLLECTION.TXT`, `AUDIO.CFG` etc.
- The **Conflicts** tab shows any files where mods overlap — the top-priority mod wins

Click **Deploy Mods** in the preview to write everything to the game folder.

---

## Restore Vanilla

Click **Restore Vanilla** to undo all mod changes and return to the original game state. Your mod list is preserved — you can redeploy at any time.
