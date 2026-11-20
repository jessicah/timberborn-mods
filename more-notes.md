WorkplaceIllumintorSpec: changes lighting of buildings?



TubeModelSpec: variant for single block, multiple visual styles?
TubeSpec: does this allow the lighting? nothing else indicates lighting...

TubeIlluminator::UpdateIlluminator() sets the color, prefering the bot over
the beaver color...

can we attach a color to a district, then get the district from a character?

---

goes in a pile:
 screwpress axles
 gold bars
 gold dust
 silver metal ingots
 solar panels

salt is an ingredient, not a food

---

Buildings\Whitepaws Faction\LightIndustry\Screwpress.Whitepaws.blueprint.json
Factions\GoodCollection.Whitepaws.blueprint.json
Factions\MaterialCollection.Whitepaws.blueprint.json
Goods\WhitepawsGoods\Liquids\Good.GrapeJuice.blueprint.json
recipes\Drinks\Recipe.Grapejuice.blueprint.json
recipes\Drinks\Recipe.Omnidrink.blueprint.json
recipes\Drinks\Recipe.OmnidrinkMed.blueprint.json
recipes\Drinks\Recipe.Omnidrinksmall.blueprint.json
recipes\Drinks\Recipe.TurboJuice_Grapes.blueprint.json
recipes\Drinks\Recipe.Wine.blueprint.json

---

PS Y:\SteamLibrary\steamapps\common\Timberborn\Timberborn_Data\StreamingAssets\Modding\Blueprints\Buildings> gci -Recurse -Include '*Folktails.blueprint.json' | foreach { jq.exe '{ name: .TemplateSpec.TemplateName, tool: .PlaceableBlockObjectSpec.ToolGroupId }' $_.FullName } | jq --slurp | jq "group_by(.tool)[] |{ToolGroup:.[0].tool, Names: [.[].name] }"

---

-a----        29/08/2026   7:58 AM            908 Good.GreenStew.blueprint.json
-a----        29/08/2026   7:58 AM            863 Good.Kimchi.blueprint.json
-a----        29/08/2026   7:58 AM            879 Good.LotusTea.blueprint.json
-a----        29/08/2026   7:58 AM            759 Good.Nitroglycerin.blueprint.json
-a----        29/08/2026   7:58 AM            871 Good.RedSoda.blueprint.json
-a----        29/08/2026   7:58 AM            779 Good.Sunfloweroil.blueprint.json
-a----        29/08/2026   7:58 AM            707 Good.Tar.blueprint.json
-a----        29/08/2026   7:58 AM            855 Good.Wine.blueprint.json


    Directory: Y:\SteamLibrary\steamapps\workshop\content\1062090\3647584961\version-1.1\Goods\WhitepawsGoods\Pileables


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        29/08/2026   7:58 AM            713 Good.Crudesawblade.blueprint.json
-a----        29/08/2026   7:58 AM            673 Good.GlassPane.blueprint.json
-a----        29/08/2026   7:58 AM            681 Good.GoldBar.blueprint.json
-a----        29/08/2026   7:58 AM            693 Good.GoldDust.blueprint.json
-a----        29/08/2026   7:58 AM            678 Good.Ironore.blueprint.json
-a----        29/08/2026   7:58 AM            670 Good.Rice.blueprint.json
-a----        29/08/2026   7:58 AM            677 Good.Rock.blueprint.json
-a----        29/08/2026   7:58 AM            663 Good.Salt.blueprint.json
-a----        29/08/2026   7:58 AM            674 Good.Saltpeter.blueprint.json
-a----        29/08/2026   7:58 AM            676 Good.Sawdust.blueprint.json
-a----        29/08/2026   7:58 AM            692 Good.Screwaxle.blueprint.json
-a----        29/08/2026   7:58 AM            715 Good.SiliconMetal.blueprint.json
-a----        29/08/2026   7:58 AM            719 Good.SolarCell.blueprint.json


    Directory: Y:\SteamLibrary\steamapps\workshop\content\1062090\3647584961\version-1.1\Goods\WhitepawsGoods\Special


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        29/08/2026   7:58 AM            676 Good.Anvil.blueprint.json
-a----        29/08/2026   7:58 AM            708 Good.ChemistrySet.blueprint.json
-a----        29/08/2026   7:58 AM            710 Good.Claypot.blueprint.json
-a----        29/08/2026   7:58 AM            788 Good.ClockWorkController.blueprint.json
-a----        29/08/2026   7:58 AM            695 Good.Drillbits.blueprint.json
-a----        29/08/2026   7:58 AM            732 Good.Educativebooks.blueprint.json
-a----        29/08/2026   7:58 AM            707 Good.GiantHalfLog.blueprint.json
-a----        29/08/2026   7:58 AM            692 Good.GiantLog.blueprint.json
-a----        29/08/2026   7:58 AM            684 Good.Hydrogen.blueprint.json
-a----        29/08/2026   7:58 AM            823 Good.LyophilizedArtificialNaturalDirtBlock.blueprint.json
-a----        29/08/2026   7:58 AM            718 Good.Mediumcauldron.blueprint.json
-a----        29/08/2026   7:58 AM            679 Good.Methane.blueprint.json
-a----        29/08/2026   7:58 AM            720 Good.MintEssence.blueprint.json
-a----        29/08/2026   7:58 AM            695 Good.Processor.blueprint.json
-a----        29/08/2026   7:58 AM            683 Good.Sensor.blueprint.json
-a----        29/08/2026   7:58 AM            716 Good.Steelsawblade.blueprint.json


    Directory: Y:\SteamLibrary\steamapps\workshop\content\1062090\3647584961\version-1.1\Goods


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        29/08/2026   7:58 AM            689 Good.Clay.blueprint.json
-a----        29/08/2026   7:58 AM            669 Good.Coal.blueprint.json
-a----        29/08/2026   7:58 AM            811 Good.Grapes.blueprint.json
-a----        29/08/2026   7:58 AM             98 Good.ScrapMetal.optional.blueprint.json


    Directory: Y:\SteamLibrary\steamapps\workshop\content\1062090\3647584961\version-1.1\Modifiers\Goods


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----        29/08/2026   7:58 AM            119 Good.Badwater_WhitepawsModifier.optional.blueprint.json
-a----        29/08/2026   7:58 AM            205 Good.Berries_WhitepawsModifier.optional.blueprint.json
-a----        29/08/2026   7:58 AM            500 Good.Clay_WhitepawsModifier.optional.blueprint.json
-a----        29/08/2026   7:58 AM            684 Good.Coal_WhitepawsModifier.optional.blueprint.json
-a----        29/08/2026   7:58 AM             51 Good.Dirt_WhitepawsModifier.optional.blueprint.json
-a----        29/08/2026   7:58 AM             51 Good.Explosives_WhitepawsModifier.optional.blueprint.json
-a----        29/08/2026   7:58 AM             79 Good.Gear_WhitepawsModifier.optional.blueprint.json
-a----        29/08/2026   7:58 AM            874 Good.Grapes_WhitepawsModifier.optional.blueprint.json
-a----        29/08/2026   7:58 AM             53 Good.Log_WhitepawsModifier.optional.blueprint.json
-a----        29/08/2026   7:58 AM             54 Good.MetalBlock_WhitepawsModifier.optional.blueprint.json
-a----        29/08/2026   7:58 AM            131 Good.PineResin_WhitepawsModifier.optional.blueprint.json
-a----        29/08/2026   7:58 AM            131 Good.Plank_WhitepawsModifier.optional.blueprint.json
-a----        29/08/2026   7:58 AM             54 Good.ScrapMetal_WhitepawsModifier.optional.blueprint.json
-a----        29/08/2026   7:58 AM            858 Good.SunflowerSeeds_WhitepawsModifier.optional.blueprint.json
-a----        29/08/2026   7:58 AM             87 Good.Water_WhitepawsModifier.optional.blueprint.json


PS Y:\SteamLibrary\steamapps\workshop\content\1062090\3647584961> gci -recurse -Include 'Good.*.blueprint.json' | jq
jq: parse error: Invalid numeric literal at line 3, column 14
PS Y:\SteamLibrary\steamapps\workshop\content\1062090\3647584961> gci -recurse -Include 'Good.*.blueprint.json' |& jq
jq: parse error: Invalid numeric literal at line 3, column 14
PS Y:\SteamLibrary\steamapps\workshop\content\1062090\3647584961> gci -recurse -Include 'Good.*.blueprint.json' | copy-item -Destination O:\OneDrive\Documents\Timberborn\Mods\Sate-a-Mole\version-1.0.8.0\Goods\Whitepaws\
PS Y:\SteamLibrary\steamapps\workshop\content\1062090\3647584961>
