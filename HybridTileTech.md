
Author: hackedpassword



# Hybrid tile tech: The birth of hybrid tiles, i.e. Bridges!

![](https://raw.githubusercontent.com/hackedpassword/Unciv-Assets/main/Images/Z2/totally_crossed_out.png)

## Reveal

The basic magic making this work:

Terrains.json:
```
	    "name": "Bridge1ocean",
	    "type": "NaturalWonder",
	    "turnsInto": "Force",  // or Hill, any terrainFeature
	    "unbuildable": true,
```

The basic assembly process looks like:

![](https://github.com/hackedpassword/Unciv-Assets/blob/main/Images/Z2/Bridge_info.png?raw=true)

_You’ll want to read on before jumping into this, there’s a bit more to it._


## How

Because the engine allows `turnsInto:` to accept a `TerrainFeature` entity as a value, apparently neither Land or Water units are implied, becoming (sort of) “whatever” (vs Any, neither, both, null). That's my observation at least.

Credit unwittingly goes to A1y0sh4 for inadvertently applying this strange behavior to Rock of Gibraltar in [the Great Unciv Rework](https://github.com/A1y0sh4/The-Great-Unciv-Rework) versions <= 2.1. I had recognized that when the Wonder tile was placed next to a Coast, unit mobility behavior acted like a canal tile. Experiments proved bridge building with this technique was possible.


## Features

Land units can cross bridge/hybrid tiles withough embarking, while Water units can cross bridge/hybrid tiles without impedement.

Not just bridges, but also, in the case of Z2, _secret water paths_ Land units can traverse using CoastTile or OceanTile.

Hybrid tiles do not count in continent calculations, meaning “attached” lands can now be split! You’ll find “Maze Island” is a different continent than the central continent even though they are adjoined by a bridge.

Advanced usage of continent splitting is possible by say, creating a Mountain as a hybrid, then bordering land to split it.

![](https://raw.githubusercontent.com/hackedpassword/Unciv-Assets/main/Images/Z2/sea_fight.jpg)

The hidden water path above hosts a land unit, non-embarked. The submarine cannot target the unit on top of the water. 

## Nuances

Getting visuals for the tiles are not quite as simple to implement as you’d think, since we're dealing with hexagonal tiles that offset in 4 out of 6 directions.

N-S in Z2 is represented by Bridge3. Tile laid down, easy peasy.

W-E in Z2 is represented by Bridge1 and Bridge2, where 1 is top, 2 is bottom. Hex tile interlacing requires a 1-2-1-2 etc pattern to establish the horizontal path for consistent aesthetics. Land units appear proper standing on tile 2, but on tile 1 they stand in the water and look weird, sure there's some solution. 

Secondly on W-E bridges, endpoints are rendered/drawn over by the next row of tiles, rendering the graphic overlays clipped. To solve this, a terrainFeature called BridgeFL (feature left) and BridgeFR (feature right) are applied to the shoreline tiles.

Angle bridges are an entire project on their own, but doable. Likely a variant of the above technique.

I implemented OceanTile with movement=0 since the game Raft crosses in one movement. Unciv would crash due to the AI zig-zagging back and forth on the water infinitly. Yairm210 figured this out using his code-ray vision. Basically, not a good idea to use zero for a movement value.


## Issues

I've explored implementing hybrid tiles with reasonable depth. Here's what I've found. There's a number of features that just do not work, or, maybe could work.

GlobalUniques.json

```
	"Double movement in [OceanTile] <for [land units] units>",
	"Double movement in [CoastTile] <for [land units] units>"
	// Land units are to receive a movement bonus that does not affect water units, doesn’t work
```
	
Terrains.json

```
 "name": "CoastTile",
	"name": "OceanTile",
	"uniques": ["Rare feature","Units ending their turn on this terrain take [30] damage",
// won't trigger:  <for [land units] units>
// Land units are to receive damage for standing around in rough seas
// Water units also take damage here which they aren’t supposed to

<except [terrainFilter] tiles>
// does not exist. Should be a way to disable building roads/railroads on hybrid tiles
```

* Wonders are bottom-layer tiles, meaning alpha transparency can’t work, so underlying terrain must be built into the Wonder tile .png image.


Units.json

```
”May not settle on [baseTerrain] tiles”
// does not exist, reviewed varieties of hacky ways to prevent settlement on hybrid tiles
```

TileImprovements.json

```
	"name": "Road",
	"name": "Railroad",
	"terrainsCanBeBuiltOn": ["Land"],
"uniques": [	"Cannot be built on ["Natural Wonder","Water"] tiles"
"Cannot be built on ["Great Improvements", "Great"] tiles"
// these don’t work. See https://yairm210.github.io/Unciv/Modders/Unique-parameters/#improvementfilter
	
	"name": "Bridge",
	"terrainsCanBeBuiltOn": ["Coast","CoastTile","Ocean"],
	// Cannot be placed on CoastTile
	// Improves Foundation (resource) but does not provide Land mobility
```

TileResources.json

```
	// 5th palace heart on the sea (oil platform) cannot use CoastTile as terrain tile, remains Coast
	// How to put resources/improvements on wonders?

	"name": "Foundation",
	"resourceType": "Bonus",
	"terrainsCanBeFoundOn": ["Coast","CoastTile","Ocean"],
	// Unable to place Foundation on CoastTile
```

## Other Hacky Efforts

There remains an uncovered hack-feature found along the way, was not able to capture it:

Settle a city adjacent to a Citadel/Great Palace (buried in the mountains direct center of the map). Upon settlement and borders established, the Improvement image should flip from GreatPalace to Citadel. I believe this is because Z2 is not a ruleset, but Citadel.png is a palace image in the Z2 mod, however when the settlement occurs, the engine falls back to the G&K image of Citadel.png, probably due to the tile `ruleVariants` not existing in either Z2/HexaRealm.json or G&K/HexaRealm.json. Note in Z2/HexaRealm.json I’ve disabled `fallbackTileSet`.

What this means is that, for instance, best case scenario, the player founds their city as above, with say NorthCastle in place of Citadel. Upon settlement, the NorthCastle image flips to NorthCastleGlow. The second image must occur in the ruleset mod, not the overlying mod. How cool would that be to have various features/terrains/improvements take on a progressive image, like cities as they progress through the eras?

Since changing Palaces from Improvements to TerrainFeatures to Wonders, I can’t seem to replicate the described behavior. It exists though! For now the final Great Palace is PalaceGlow, a TerrainFeature.


