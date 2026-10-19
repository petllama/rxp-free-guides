# Free RestedXP Guides for Polestar (unofficial)

The free World of Warcraft: Forever leveling guides that RestedXP publishes in
its [RXPGuides](https://github.com/RestedXP/RXPGuides) repository, converted to
the guide format of [Polestar](https://github.com/fitzforge/polestar).

This is a **community addon for Polestar**. It is **not made, endorsed or
supported by RestedXP or by Polestar**. Report problems with it here, not to
either of them.

## What's in it

108 guides for levels 1 to 23, both factions, in Polestar's guide menu:

| Menu | Guides | Played as |
|---|---|---|
| Leveling (no folder) | the speedrun routes for every start zone, including Skyborne | solo, softcore |
| RestedXP · Speedrun Guide Mage / Mage AoE, ADV AoE Alliance Mage | the Mage and AoE-Mage routes | solo, softcore |
| RestedXP · Dungeon Guide 1-20 / 1-22 | the routes with dungeon detours | in a group, softcore |
| RestedXP · RXP Survival Guide 1-20 | the safer (hardcore) routes | solo, hardcore |

Each guide hands over to the next with `next`, the way the original does,
within this pack. Where the original hands over to a paid RestedXP guide (past
level 22), the guide simply ends.

## Install

1. Install **Polestar 0.2.6 or newer** first.
2. Download `PolestarPack_RXPFree-<version>.zip` from this project's
   [releases](https://github.com/petllama/rxp-free-guides/releases) and unzip it
   into `Interface/AddOns/`, next to `Polestar`.
3. Restart the game. The guides show in Polestar's guide menu
   (`/polestar guides`) under Community guides; Options › Community guides
   (`/polestar packs`) turns the addon on or off.

## How it differs from the original

The conversion is automatic. The route, the quests and the notes are
RestedXP's; how they run is Polestar's. Known differences:

- **The play style is fixed per guide.** RestedXP picks steps live for solo or
  group, softcore or hardcore, self-found or not, and your XP rate. Polestar
  has no such settings, so each guide was converted for the style in the table
  above, with the auction house available and 1× XP. Steps for other styles
  are left out.
- **Some step conditions are gone.** Polestar can't check your money, whether
  you know a spell, or a profession or reputation level. Steps that RestedXP
  shows only under those conditions always show here. In practice:
  class-training steps list every spell the original offers at that visit.
  Skip a spell you can't afford yet.
- **Along the way.** RestedXP's background objectives (`#completewith`,
  `#sticky`) are Polestar's *Along the way* list. Path points and actions
  Polestar can't check off there (vendoring, using an item without a quest)
  are notes, or are left out, rather than staying in the list.
- **"Or" conditions** are split into one step per case.

[`reports/`](reports) lists every condition and goal the conversion dropped or
changed, per guide.

## Licence and attribution

The guides are an adaptation of RestedXP's free guides:

- **Source:** [RestedXP/RXPGuides](https://github.com/RestedXP/RXPGuides),
  the files listed in `Guides/GuideList-forever.xml`, at the commit named in
  [SOURCE.md](SOURCE.md). © RestedXP and the RXPGuides contributors.
- **Licence of the source:** [Creative Commons
  Attribution-NonCommercial-ShareAlike 4.0
  International](https://creativecommons.org/licenses/by-nc-sa/4.0/).
- **Changes:** converted to Polestar's `.guide` format: coordinates
  reprojected, quest, NPC and item references resolved against Polestar's
  reference data, step logic rewritten as described above, and text the
  format can't carry dropped. RestedXP's addon code isn't included.

This adaptation is licensed under the same **CC BY-NC-SA 4.0** licence (full
text in [LICENSE](LICENSE)). You may share and adapt it, with attribution,
**not for commercial purposes**, and under the same licence. That means no
paid downloads, no ads and no addon-site reward programmes for it or its
derivatives.

The built addon also contains facts from Polestar's reference data (quest,
NPC and map data), which Polestar's compiler places in it. Polestar's
[licence exception](https://github.com/fitzforge/polestar/blob/main/LICENSE-EXCEPTION.md)
lets a compiled pack carry them under the pack's own terms.

"RestedXP" names the source of the guides; no trademark rights are claimed.

## Building it

The pack is built from the `.guide` files in `guides/` with Polestar's own
tools (Node 24+, Lua 5.1, a Polestar clone with `npm link`):

```sh
polestar lint       # check the guides against the game's data
polestar playtest   # play every guide to the end in the real addon
polestar pack       # write the release zip to dist/
```

The `.guide` files are generated. Fix a problem in a guide by opening an issue
here: hand edits are lost at the next conversion from a newer RestedXP source.
