# PF2e Relic Rarity

**PF2e Relic Rarity** is a Foundry Virtual Tabletop v14 module for the Pathfinder Second Edition system. It expands item-rarity presentation without replacing PF2e's native item data model.

## Features

- Configurable rarity colors for Common, Uncommon, Rare, Epic, Mythic, Legendary, Artifact, Demi-divine, Divine, Aeterna, and Unique.
- Inventory item names and native PF2e rarity badges follow the configured rarity appearance.
- Optional animated icon effects and loot beams.
- Per-rarity presentation, pickup, and drop sounds with Foundry's native file picker.
- GM **Present Item** action that shows the item's name, image, rarity, and description to connected players.
- Automatic rarity scoring for weapons, armor, and shields based on runes, special materials, socketed Aeon Stones, and the item's unmodified PF2e base level.
- Aeon Stone socketing for eligible armor. The stone is stored in the armor and its Rule Elements are injected into the armor while socketed.
- Owner players can insert, replace, and remove socketed Aeon Stones.
- Loot-drop presentation with rarity-dependent beams and sounds.
- English and French localization.

## Compatibility

- Foundry Virtual Tabletop: **v14**
- Pathfinder Second Edition: **8.0.0+**, verified with **8.1.2**

## Installation

Use this manifest URL in Foundry VTT's **Install Module** dialog:

```text
https://raw.githubusercontent.com/yfgi21/pf2e-relic-rarity/main/module.json
```

Or download the current ZIP from `dist/` and extract it under `Data/modules/`.

## Default rarities

| Rarity | Default color |
|---|---|
| Common | PF2e/native inventory color |
| Uncommon | `#6fcf68` |
| Rare | `#4f9fdf` |
| Epic | `#a97bdc` |
| Mythic | `#c43d63` |
| Legendary | `#d98a32` |
| Artifact | `#6b0000` |
| Demi-divine | `#f0d46a` |
| Divine | `#ffd700` |
| Aeterna | `#ffe16a` |
| Unique | `#000000` |

All defaults can be customized by the GM.

## Equipment rarity calculation

The module does not overwrite PF2e's native Common / Uncommon / Rare / Unique data. Native Uncommon and Rare items remain at least Uncommon or Rare visually, while PF2e Unique remains Unique.

For weapons, armor, and shields, the Alpha power score is capped at **20**. The enhancement component is derived from runes, special materials and, for armor, a socketed Aeon Stone. The object's base PF2e level is detected before rune-derived adjustments and contributes `floor(base level / 2)`.

Default score bands:

- 0-3: Common
- 4-7: Uncommon
- 8-11: Rare
- 12-15: Epic
- 16-18: Mythic
- 19-20: Legendary

Higher narrative tiers require a score of 20 plus a sufficiently powerful base item: Artifact, Demi-divine, and Divine are progressively gated by the base level. Aeterna remains GM-controlled.

## Upgrading from Alpha PF2e Rarity

The public package uses the new package ID `pf2e-relic-rarity`. On first GM load it attempts to migrate existing world settings and document flags from the former `alpha-pf2e-rarity` namespace. Do not enable both modules at the same time.

## Notes

This module is an independent Foundry VTT add-on for the PF2e system. It does not redistribute Pathfinder compendium content, rules text, or Paizo artwork.

## Support

Issues and feature requests: https://github.com/yfgi21/pf2e-relic-rarity/issues
