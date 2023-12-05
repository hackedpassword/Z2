
# Z2 : Zelda 2 for Unciv

Looking for some NES nostalgia? With a Civ V twist? You’ve come to the right place.

![](https://raw.githubusercontent.com/hackedpassword/Z2/main/preview.png)

In case you missed it, **[Issues](https://github.com/hackedpassword/Z2/issues) (dev-related) and [Discussions](https://github.com/hackedpassword/Z2/discussions) (game-related) at the top of the page** have their respective community presences for players, modders, coders, whoever! Become a part of the Z2 party! 

I’m a huge fan of the original Zelda 2, up to and including no-lives-lost vanila game completion. I also have a [less than 7 minute completion speedrun time](https://youtu.be/uHrhG_AkObw) which you may find entertaining. ;) 

### Z2 has some notable achievements:

1. For the first time in Unciv history, bridge tiles can be placed. This is accomplished with [Hybrid Tile Tech](HybridTileTech.md), invented here, and now [mentioned in Unciv's code](https://github.com/yairm210/Unciv/blob/11108112b513da41fe80875c01332650455f1196/core/src/com/unciv/models/ruleset/validation/RulesetValidator.kt#L352).
2. Thanks to hybrid tiles, three specific Zelda 2 gameplay elements have been preserved: raft crossing, boot water walking, and the bridge to Maze Island.
3. Unciv modder/mappers are going to have a field day tearing apart Z2! Have at it! Share what you learned, this is a huge opportunity!

## Before:

![](https://raw.githubusercontent.com/hackedpassword/Unciv-Assets/main/Images/Z2/Z2_before.png)

## After:
![](https://raw.githubusercontent.com/hackedpassword/Unciv-Assets/main/Images/Z2/Screenshot_20231006_182203.jpg)

Take a closer look at the above and you'll see the **hidden water paths** using [Force](https://github.com/hackedpassword/Z2/blob/a28fc4ceebfa023fb7481dfcedd35cacc9fe58d3/jsons/Terrains.json#L282) (a TerrainFeature) via [customized ocean Hybrid tiles](https://github.com/hackedpassword/Z2/blob/a28fc4ceebfa023fb7481dfcedd35cacc9fe58d3/jsons/Terrains.json#L791) that makes the special features of the Hyrule overworld map possible! 

[Version notes](https://github.com/hackedpassword/Z2/version_notes.md)

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
