toolbar:

- cut trees
- plant crops
- plant trees
- demolish
- priority
- paths
- landscaping
- storage
- district
- housing
- water
- food
- wood
- metal
- power
- science
- automation
- well-being
- decorations
- monuments

template name fixes: 3664330262
logstairs:  3281774771
leafcoats:  3552203634
whitepaws:  3647584961
emberpelts: 3346318229
folktails: <builtin>
ironteeth: <builtin>
adaptors have whitepaws: 3713117382

grapes, green grapes... really need to fix this one (don't want both)

birch, pine, oak, succulent -- assign a faction

parsnips -- shouldn't exist with FT+IT+EP+LC adaptors

sunflower seeds, has the need been removed? seems so... what other needs are
missing?

sugarcane -- same issue as parsnips??

# Whitepaws

SoupHand.Whitepaws toolbar icon => LiquidStorageLodge.Whitepaws

## with whitepaws, do we want to separate into green + red grapes again?

`GrapeJuice` is a constant pain...

when overriding parts of a blueprint, the file paths have to match!

change `GoodGroupId` for various things

- REMOVE "Construction materials"
- REMOVE "Materials"
- REMOVE "Water"
- REMOVE "Buildings core elements"
- REMOVE "Plans"

re-use existing:

- Piles
- Warehouses
- Tanks (+ Gas)
- Drinks
- Ingredients (only foods!!!)
- Food

# Tool Groups

- More Platforms: do I want on the main toolbar??
- Dams, Houses, and Damhouses > Dam > Giant Log Dam (2W), Giant Log Dam (L):
	move to Whitepaws > Primitive Dams (rename to Dams)
	WP > Wooden Reservoirs > Floodgate Dam => WP > Dams
- WP specialist houses => WP > Housing
- Basic Village Structures => into WP

## The Standard Layout

- Pointer
- Cut Trees
- Plant Crops
- Plant Trees
- Demolish
- Priority

- Paths
- Landscaping
- Storage
- Districts
- Housing
- Water
- Food
- Logs
- Metal
- Power
- Science
- Automation
- Wellbeing
- Decoration
- Monuments

- Options

## Modified (Moles)

The Faction Menu is defined in:

Sort-a-Mole\version-1.0.8.1\Mole\Cadre\Groups\<Faction>\Faction.MoleCadre.<Faction>.blueprint.json

A rather insane path, can probably simplify...

Problem: some sub-menus overflow due to not being centered

- Tooltip (Pipette tool)
- More platforms (mod)
- Dams, Houses, and Damhouses > Dam > Giant Log Dam, Giant Log Dam (bug: should
  be in Water Beavers)
- Tree Structure > Treetrunk Overhang 1x2 (bug: should be in Leaf Coats)
- Basic Village Structures > Seamstress Lodge, Help > * (bug: should be in Water
  Beavers)
- Automation > * Sensors, One Block * (mod: move into the Other menu)
- Trains (Choo!Choo! mod, okay here)

- Other > Storage (bug: Water Beavers here instead of under Water Beavers)
	- 1x2x2 storages (feat (moles): put in faction storages)
	- Warm Storage Pot
	- Advanced Warm Storage
	- Scroll Display
	- Underground Cold Storage
- Other > Metal
	- Scavenger Flag (minor)
	- Forge
	- Primitive Smelter
	- Wood Burner
- Other > Wood > Logging > Logging Loft
- Other > Water & Badwater 
	- Water Pump (and sub-items)
	- Irrigation (and sub-items)
	- Valve Lodge
	- Aqueduct (and sub-items)
- Other > Food (and sub-items)
- Other > Monuments
	- Tree of Life: per faction?
- Other > Decoration: move to factions
- Other > Power
	- Shafts & Tunnels: per faction?
	- Water Beavers
- Other > Paths
	- Logstairs: per faction?
	- Water Beavers

## The Faction Sub-Menu Layout

- Hauling Post => Districts Management
- Builders Hut => District Management
- District Center => District Management
- Routes => Rename to Paths, collapse to single menu
- Platforms; Wooden Reservoirs; Valves, Seals, Pipes, Etc; Landscaping =>
  collapse into Landscaping
- Housing
- Food
- Water (aka Fluids)
- Logs
- Progress (metal + science)
- Power
- Piles => Storage
- Tanks => Storage
- Warehouses => Storage
- Batteries => Power (gravity battery, flywheels)
- Health => Wellbeing
- Pleasures => Wellbeing
- Covers => Decoration
- Decor => Decoration
- Monuments

## The Whitepaws sub-menu is completely broken...

- Pit & Ladder Lodge (Haulers with Side Door) => District Management
- Pit & Ladders Lodge (Haulers Tower Segment) => District Management
- Hauling Bot Standby Area => District Management OR Progress/Science
- Builder Lodge => District Management
- Pit & Ladder Lodge (Builders with Side Door) => District Management
- Pit & Ladder Lodge (Builders Tower Segment) => District Management
- Four-ways District Center => District Management
- Loggers, Basic Crafters, Etc => Use Water Beavers layout, currently overflows

## Overflowing Menus

Decor, Pleasures, Health, ...

# Powershell & JQ

gci -recurse -include '*.blueprint.json' | foreach { jq '{name:
.TemplateSpec.TemplateName, tool: PlaceableBlockObjectSpec.ToolGroupId} |
select(.name != null) | select(.tool == \"Paths\")' $.FullName | jq --slurp ". |
[.[].name]"

## A Better Way!

```ps
gci -Recurse -Include '*.blueprint.json' |
	foreach {
		jq.exe '{ name: .TemplateSpec.TemplateName, tool: .PlaceableBlockObjectSpec.ToolGroupId }' $_.FullName
	} |
	jq.exe --slurp |
	jq.exe "group_by(.tool)[] | { ToolGroup: .[0].tool, Names: [.[].name] }"
```

## Current Layout

An alternate approach might be to order the Faction menus by sub-menu length?

More Platforms: has Folktails & IronTeeth, move into those?



### Folktails

Paths and Structures overflows
	> Paths
	> Ziplines
	> Bridges
	> Platforms
Decoration overflows

### IronTeeth

Paths and Structures overflows
	> Paths
	> Tubeways
	> Bridges
	> Platforms
Decoration overflows

### Emberpelts

Paths and Structures overflows
Has separate Platforms and Overhangs
Has separate Tubeways
Landscaping overflows
Decoration overflows

### LeafCoats

Paths and Structures overflows
Has separate Platforms and Overhangs
Has separate Ziplines
Tree Structure overflows
Has custom Dams
Well-Being overflows
Decoration overflows

### Whitepaws

# Gah

Goods group spec with id Materials not found... selecting item in Tank

