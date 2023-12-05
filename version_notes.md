## Game notes

In progress: v1.2

Version 1.0:

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
