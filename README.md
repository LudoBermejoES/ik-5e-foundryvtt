# Iron Kingdoms 5E (IK5E)

A Foundry VTT module containing content from **Iron Kingdoms: Requiem** for the D&D 5th Edition game system.

## Requirements

- Foundry VTT v12 or v13
- D&D 5E System v4.0.0+

## Installation

### Manual Installation
1. Download or clone this repository
2. Copy the `ik` folder to your Foundry VTT `Data/modules/` directory
3. Restart Foundry VTT
4. Enable the module in your world's Module Management

### Manifest URL
```
[Coming Soon]
```

## Content

### Races (12)
**Non-Human Races:**
- Gobber
- Iosan
- Nyss
- Ogrun
- Rhulic Dwarf
- Trollkin

**Human Nationalities:**
- Cygnaran
- Khadoran
- Llaelese
- Ordic
- Cryxian (Scharde)
- Protectorate of Menoth

### Classes (5)
- **Alchemist** - Master of alchemical formulas and compounds
- **Gun Mage** - Arcanist who channels magic through firearms
- **Gunfighter** - Expert marksman and firearms specialist
- **Mechanik** - Engineer of steamjacks and mechanika
- **Warcaster** - Warrior-mage who commands warjacks

### Subclasses (15)

**For Existing D&D Classes:**
- **Barbarian:** Path of the Bloodrager
- **Bard:** College of Battle Chroniclers
- **Cleric:** Benefaction Domain, Guile Domain, Obedience Domain
- **Fighter:** Man-at-Arms, Storm Knight
- **Monk:** Way of the Iron Ascetic
- **Paladin:** Oath of Radiance, Oath of the Wall
- **Ranger:** Bounty Hunter, Mage Hunter, Vigilant
- **Rogue:** Cutthroat, Duelist

### Backgrounds (13)
- Arcane Order Initiate
- Cygnaran Military
- Golden Crucible Member
- Greylord
- Khadoran Military
- Llaelese Resistance
- Mercenary Veteran
- Order of Illumination
- Pirate
- Priest
- Steamjack Handler
- Trencher
- Urban Investigator

### Feats (25)
**Essence Feats** - Special feats tied to the optional Essence system:
- **Intellectual:** Battlefield Coordinator, Genius, Prescient, Quick Thinking, Vigilant
- **Mighty:** Beat Back, Bounding Leap, Invulnerable, Tough As Nails, Vigorous
- **Agile:** Cagey, Deft, Untouchable, Virtuoso, Watchful
- **Gifted:** Dominator, Fast Caster, Magically Sensitive, Resolute, Student of the Arcane
- **Pious:** Ascetic, Blessed with Health, Chosen by the Gods, Holy Aegis, Shield of the Believer

### Equipment

**Weapons (57):**
- Simple Melee (bayonet, coal shovel, gaff, harpoon, knuckledusters, etc.)
- Simple Firearms (pistol, musket pistol, repeating pistol, rivet gun, blunderbuss, etc.)
- Martial Melee (caspian battleblade, chain blade, cutlass, nyss claymore, etc.)
- Martial Firearms (hand cannon, magelock pistol, carbine, heavy rifle, etc.)
- Storm Weapons (storm glaive, electro lance, voltaic halberd)
- Grenades (explosive, incendiary, smoke, flash, fear gas, strangle gas)

**Armor (12):**
- Light (alchemist's leathers, warcaster armor light)
- Medium (armored apron, infantry armor, tailored plate, warcaster armor medium)
- Heavy (storm knight armor, steam armor, warcaster armor heavy)
- Shields (assault shield)
- Clothing (armored greatcoat)

**Gear & Tools (17):**
- Ammo bandolier, gas mask, goggles, gun brace
- Field alchemy kit, forensic kit, gunsmith's kit, mechanik's toolkit, rune-etching kit
- Ammunition (light rounds, heavy rounds, slugs)

### Alchemical Formulas (17)

**Common:**
- Alchemical Acid, Alchemical Restorative, Antitoxin, Black Oil
- Bottled Light, Firebane Salve, Healing Liniment, Night's Black, Vitriolic Fire

**Uncommon:**
- Alchemical Explosive, Ashes of Urcaen, Fear Gas, Fortemorphic Elixir
- Persuasion Elixir, Rust Agent, Somnolence Elixir, Spirit Salts

### Magic Items (5)
- Firebrand
- Fellblade
- Orgoth Staff
- Relic Blade
- Greylords Rune Axe

### Pregenerated Characters (12)

Ready-to-play characters for Iron Kingdoms campaigns. JSON files in `docs/foundry_actors/`.

**Aldea de Espíritus Adventure:**
- Dmitri Volkov - Paladin 1 (Human Khadoran)
- Gorluk Tharok - Fighter 1 (Ogrun)
- Ivan Starov - Bard 1 (Human Khadoran)
- Misha Krasnov - Rogue 1 (Human Khadoran)
- Grindar Bloodborn - Ranger 1 (Trollkin)
- Yuri Koskov - Cleric 1 (Human Khadoran)

**Cabeza Férrea Adventure:**
- Brokk Steadfast - Cleric 1 (Urban Trollkin)
- Elias Dunford - Rogue 1 (Human Cygnaran)
- Torgun Ironbid - Fighter 1 (Rhulic Ogrun)
- Nola Carvalo - Gun Mage 1 (Human Ordic)
- Gek-Darabin - Alchemist 1 (Gobber)
- Hilda Forgebloom - Mechanik 1 (Rhulic Dwarf)

## Languages

This module supports localization. Currently available:
- English (en)
- Spanish (es) - Partial

To contribute translations, edit the files in the `languages/` folder.

## Compiling Compendiums

The module includes source YAML files in `packs/_source/`. To compile them into LevelDB packs:

```bash
# Install Foundry CLI tools
npm install -g @foundryvtt/foundryvtt-cli

# Navigate to module directory
cd /path/to/ik

# Compile all packs
fvtt package pack ik-races --yaml
fvtt package pack ik-classes --yaml
fvtt package pack ik-subclasses --yaml
fvtt package pack ik-backgrounds --yaml
fvtt package pack ik-feats --yaml
fvtt package pack ik-weapons --yaml
fvtt package pack ik-armor --yaml
fvtt package pack ik-equipment --yaml
fvtt package pack ik-consumables --yaml
fvtt package pack ik-magic-items --yaml
```

## Development

### Generating Character JSONs

Characters are defined in markdown at `/Users/ludo/code/RdH/docs/aventuras/` and converted to Foundry JSON:

```bash
cd /Users/ludo/code/ik/tools

# Convert all characters from an adventure
python3 characterConverter.py /path/to/adventure/folder -o /Users/ludo/code/ik/docs/foundry_actors
```

The script:
- Loads item databases from `tools/foundry_export_es/` (Spanish IK content) and D&D 5e sources
- Embeds class, race, background, equipment, and spells as items in the actor
- Maps Spanish spell names to English D&D 5e compendium entries

See `CLAUDE.md` for detailed documentation.

### Dependencies

```bash
pip install pymupdf pyyaml
```

## License

This module is a fan-made conversion of content from Iron Kingdoms: Requiem.
Iron Kingdoms is a trademark of Privateer Press, Inc.
This module is not affiliated with or endorsed by Privateer Press.

## Credits

- **Iron Kingdoms: Requiem** by Privateer Press
- **D&D 5th Edition System** for Foundry VTT
