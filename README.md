
# Z2 : Zelda 2 for Unciv

Looking for some NES nostalgia? With a Civ V twist? You’ve come to the right place.

![](https://raw.githubusercontent.com/hackedpassword/Z2/main/preview.png)


I’m a huge fan of the original Zelda 2, up to and including no-lives-lost vanila game completion. I have a [less than 7 minute completion speedrun time](https://youtu.be/uHrhG_AkObw).

### Z2 has some notable achievements:

1. For the first time in Unciv history, bridge tiles can be placed. This is accomplished with [Hybrid Tile Tech](HybridTileTech.md), invented here, and now [mentioned in Unciv's code](https://github.com/yairm210/Unciv/blob/11108112b513da41fe80875c01332650455f1196/core/src/com/unciv/models/ruleset/validation/RulesetValidator.kt#L352).
2. Thanks to hybrid tiles, three specific Zelda 2 gameplay elements have been preserved: raft crossing, boot water walking, and the bridge to Maze Island.
3. Unciv modder/mappers are going to have a field day tearing apart Z2! Have at it! Share what you learned, this is a huge opportunity!

## Before:

![](https://raw.githubusercontent.com/hackedpassword/Unciv-Assets/main/Images/Z2/Z2_before.png)

## After:
![](https://raw.githubusercontent.com/hackedpassword/Unciv-Assets/main/Images/Z2/Screenshot_20231006_182203.jpg)

Take a closer look at the above, and you'll see the hidden water paths using Force (TerrainFeature) via hybrid tiles! 

## Game notes

Version 1.0!

Converted the mod from an extension mod to a base ruleset. This means it no longer relies on the G&K assets, becoming a stand-alone mod.

- Tech tree feeling good looking great
- Numerous updates to units/buildings for the new tech tree
- The conversion also means the Prehistoric era can be merged back in next version
- New Villager actions for early eras with tile and icon graphics
- Cleaned up lava flows at Cave tiles
- All towns now grant individual promotions specific to the spell learned, and sword skills learned

Updates to v0.9 (with some augmentation from 0.8):

I'm focusing on the Unciv side atm, producing unit/weapons updates. These mind late and end-game gameplay. I've added a few additional new unit/weapons in 0.8 and are advancing these in 0.9.

Lots of commenting in the json configs, including what could be perceived as story elements detailing how/why certain attributes are or came to be.

- GDR MK-II, and MK-III - the latter available with Future Tech and utterly destructive. Think MW/Behemoth. Custom (temp-experimental) sprites for these. The MK-II on its own is fierce.
- Applied logical attributes to various units, maybe TUGR-style. i.e., tanks now are ranged and have attack/def modifiers.
- Some unit abilities do not activate until triggered via tech or buildings (this doesn't work correctly everywhere, suspecting bug)
- Much work has been placed into ordnance. Whereas guided missiles for instance have historically been as effective as stink bombs, they now find practical use. In this instance generally 3 GM's can finish off a 50% gunpowder unit.
- Bunker busters generally do 50-66% dmg to cities. Each req's 1 aluminum, only carried by a nuclear sub atm, or deployed by a city.
- Nuclear bunker busters are 1-tile city obliterating WMD's. Procuring just one is very resource heavy. These will wipe a city off the map.
- Cruise missiles, i.e. Tomahawks, have great range, and do very reasonable damage to units that make big targets. Can one-shot numerous units - fun toy, til the enemy sends one back.
- Nuclear missilies have a new variant, the ICBM, with a strength and blast of 3.
- The most destructive TSAR bomb has a blast of 6 - it is a civilization destroyer. Obtaining one of these is no easy task.
- Clever use of tech discovery is needed to obtain powerful units/weapons.
- Helicopter gunship has dual missile pods (can carry two guided missilies, think Apache) and-or also a bunker buster as payload. Strong attacker, can be smashed quickly by armored units. Does not embark (phew!!).
- Anti-air units can carry a missile. They can also intercept missiles, making them quite important in defending against this modern onslaught of rocket-propelled weaponry.
- There are conversion buildings for horse/iron/oil resources, making use of stale resources that never get used later in the game.
- UnitTypes have been updated to better align logical interactions of units/weapons.
- Modern Armor now receives triggered [modern] stealth upgrade.
- Deep Ocean tiles create soft clips against general transit, and fast transit for carriers and nuclear subs.
- Lots of other smaller updates, WIP.

Release 8 (v0.8)

> _Info on current version 0.9 follows the FAQ below. If you look on the right, you'll see 0.8 is encapsulated as a Release, if stability is needed (because I commit straight to main while at zero-dot versions). But Z2 is not popular atm, so I can totally get away with this LOL._

- Workers are original Villagers, and change their form every era!
- WMD's and new GDR's for late/end games
- Deep Ocean creates soft clips where areas of vast ocean has no gameplay
- Towns and Palaces are properly named per the originals
- Tile add/updates: Cavern, Forest, Kasuto Ruins
- Villagers can build Boulders
- Rivers are now called Lava
- Lots of config tweaks/bug fixes

Palaces provide a powerup for scaling the mountainous landscape to adjacent land units, which will later be refined and aligned to each palaces' unique item. Towns heal units (healer house).

All places, power-ups, bonuses, etc are found as expected in a very detailed interpretation of the original Zelda 2 game. Converting from square tiles to hex tiles was challenging, but the challenge was met!

The map was built with purists in mind. Take Maze Island for instance. Super challenging to make an approximation of the paths within the constraints of the scale.

## Modder notes

Feel free to review/reuse the json’s. Ask questions in discord. I've gained a lot of experience implementing hybrid tiles.

In the future I’ll be moving the ./image/ assets over to my [assets repo](https://github.com/hackedpassword/Unciv-Assets/images/Z2/) to reduce the mod size and build the atlas as needed.

Comment in the [discord](https://discord.com/channels/586194543280390151/1138883296835682324) channel. Would like to hear your feedback.


## Credits are due!

- [The Spriters Resource]( https://www.spriters-resource.com/) for fantastic sprite sheets.
- Included are credits to the sprite rippers: [Mister Mike](https://www.spriters-resource.com/submitter/MisterMike/), Obreck, [Bruice Juice](https://retrogamezone.co.uk/zelda2.htm), [Rick N. Bruns](https://www.pinterest.com/snesmaster/) (that partial original map above) - huge thanks for creating that map!
- Everyone’s images on the net I used for visual reference.
- Ninendo including my NES and my copy of Zelda 2.
- Myself for upcoming audio samples from the game for in-game Z2 use.
- Myself for ripping sprites from the sheets and converting them to hex tiles.
- Yairm210 for Unciv and Unciv assets and amazing documentation.
- SomeTroglodyte for his massive contributions including debugging complex Z2 issues.
- [A1y0sh4](https://github.com/A1y0sh4/The-Great-Unciv-Rework) and [Indonesian Gentleman](https://github.com/carriontrooper/Alpha-Frontier) for the relentless references I made to understand Unciv modding via their mods.
