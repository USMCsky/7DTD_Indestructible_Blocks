# 7DTD Indestructible Blocks
![Version](https://img.shields.io/badge/Version-3.0-blue?style=for-the-badge)
![GitHub last commit](https://img.shields.io/github/last-commit/USMCsky/7DTD_Indestructible_Blocks?style=for-the-badge)
![Language](https://img.shields.io/badge/Language-XML-orange?style=for-the-badge)
![Author](https://img.shields.io/badge/Author-USMCsky-blue?style=for-the-badge)

A lightweight **7 Days to Die XML modlet** that adds claim-safe, indestructible utility blocks with shape selection and radial pickup support.

## Core Mechanics & Features

### 📐 Shape Menu Functionality
When you hold the block in your hand, press and hold your **Reload key (`R`)** to open the radial menu, then select **Shapes** to choose wedges, plates, columns, and more.

### 🛡️ Current 3.0 Placement Behavior
The older `Place="OnlyInClaim"` hook no longer exists in 7DTD 3.0. This mod now stays XML-only and load-safe, so placement follows the normal game block-placement rules instead of a hard claim-only restriction.

### 🎒 Radial Pickup
To reclaim the block, the original player can look at any placed shape, hold **Interact (`E`)**, and select the **hand icon** from the radial wheel.

---

## Installation

1. **Download or clone** this repository.
2. Ensure your game uses the standard **Mods** folder:
   - Typical path: `.../7 Days To Die/Mods/`
3. Place the mod folder so the structure looks like:

```text
7 Days To Die/
└── Mods/
    └── 7DTD_Indestructible_Blocks/
        ├── Config/
        ├── ModInfo.xml
        └── (other mod files)
```

4. Launch the game and load your world/server.

## Usage

- Craft or obtain the indestructible block item in-game.
- Place the block anywhere the normal game rules allow.
- Use **`R`** while holding the block to choose alternate shapes.
- Use **`E`** on a placed block and select the hand icon to pick it back up.

## Compatibility Notes

- Designed as an XML modlet for modern 7DTD mod loading via the `Mods` directory.
- If using multiple block-editing mods, load-order conflicts can occur when multiple mods patch the same block definitions.
- For dedicated servers, install the mod on the server first, then client-side if your setup requires it.
- Upgrades now craft a new fixed block ID, `indestructibleSteelShapes`, while the old `indestructibleSteelBlock` entry is kept as a hidden legacy ID so existing saves do not reshuffle block mappings.
- Do **not** remove or rename deployed block definitions from an active world without a backup. In 7DTD that can remap saved block IDs and damage unrelated tile-entity inventories.

## Troubleshooting

- **Mod fails to load with `No block placement class 'OnlyInClaim' found`:** That property was removed in 3.0. This repo now removes it so `blocks.xml` loads cleanly again.
- **Shapes not appearing:** Verify no other mod overrides the same block/item entries.
- **Red `TileEntityComposite.read` spam after updating the mod:** A world that already saved the earlier broken block may still contain incompatible active-block data. Restore a backup from before that version, or replace the affected save/region data before using the fixed build.
- **Generators/turrets lost contents after mod removal:** That is a save-compatibility failure, not normal mod behavior. Keep the legacy block ID in place and do not uninstall or rename block defs on a live world without a tested rollback plan.
- **Mod not loading:** Double-check folder nesting (avoid accidental extra parent folder levels).

## Credits

Created by **USMCsky**.
