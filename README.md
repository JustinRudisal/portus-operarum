# Portus Operarum

A lore-friendly workforce-sharing wharf mod for Anno 117, inspired by the commuter pier from Anno 1800. This mod enables workers to commute between islands, helping to alleviate labor shortages and create interconnected island economies.

## Features

- **Workforce Transportation**: Dedicated harbor structure that facilitates worker commuting
- **Inter-Island Labor Sharing**: Connect multiple islands to balance workforce distribution
- **Commuter Ferry System**: Transport workers efficiently between connected islands
- **Commuter Stations**: Public service buildings for worker pickup and dropoff
- **Progressive Unlocks**: Unlock advanced features as your empire grows

## Installation

### Prerequisites

- Anno 117 (base game)
- Anno 117 Mod Loader (if required by your mod management tool)

### Manual Installation

1. Download or clone this repository
2. Copy the entire `portus-operarum` folder to your Anno 117 mods directory:
   - **Default Path**: `Documents/Anno 117/mods/`
   - Create the `mods` folder if it doesn't exist
3. Launch Anno 117
4. The mod should automatically load and be active in-game

### Using iModYourAnno (Recommended)

1. Open iModYourAnno
2. Click "Add Mod" and select the mod folder
3. Enable "Portus Operarum" in your mod list
4. Launch the game through iModYourAnno

## Mod Structure

This mod follows the standard Anno 117 mod structure:

```
portus-operarum/
├── modinfo.json                 # Mod metadata and configuration
├── data/                        # Game data modifications
│   └── config/
│       └── export/
│           └── main/
│               └── asset/
│                   └── assets.xml           # Main asset definitions
├── assets/                      # Additional asset definitions
│   └── buildings/
│       └── building_definitions.xml         # Building templates
├── texts/                       # Localization files
│   ├── english/
│   │   └── portus_operarum_english.xml     # English translations
│   └── german/
│       └── portus_operarum_german.xml      # German translations
├── gui/                         # User interface modifications
│   └── templates/
│       └── portus_operarum_gui.xml         # Custom UI templates
└── README.md                    # This file
```

## Key Files Explained

### modinfo.json

The mod's main configuration file containing:
- **Version**: Current mod version (semantic versioning)
- **ModID**: Unique identifier for this mod
- **Dependencies**: Required DLCs or other mods
- **Metadata**: Author info, description, known issues

### data/config/export/main/asset/assets.xml

Core asset definitions using ModOps XML:
- **ModOp Type="addNextSibling"**: Creates new assets based on existing ones
- **ModOp Type="merge"**: Modifies existing game assets
- **GUID System**: Uses placeholder GUIDs starting from 1742000000

### assets/buildings/building_definitions.xml

Detailed building templates demonstrating:
- **Production Buildings**: Transform resources and provide services
- **Public Services**: Enhance resident satisfaction
- **Harbor Structures**: Special waterfront buildings
- **Decorative Elements**: Aesthetic improvements
- **Upgrades**: Enhancement items for buildings

### texts/[language]/

Localization files providing in-game text:
- Building names and descriptions
- UI labels and tooltips
- Status messages and notifications
- Supports multiple languages (English, German included)

### gui/templates/

Custom UI element definitions:
- Info panels for buildings
- Custom buttons and controls
- Statistics displays
- Property bindings for dynamic content

## GUID Registry

GUIDs are unique identifiers for all game assets. This mod uses the following GUID ranges:

| Range | Purpose |
|-------|---------|
| 1742000001-1742000009 | Main buildings (Portus Operarum, etc.) |
| 1742000010-1742000019 | Production buildings |
| 1742000020-1742000029 | Resources and products |
| 1742000100-1742000199 | UI text elements |
| 1742000200-1742000299 | Status messages |

**Important**: When adding new assets, always increment the GUID by 1 and update this registry to avoid conflicts.

## Development Workflow

### 1. Planning Phase

- Define your feature or building
- Determine required assets (buildings, resources, UI)
- Allocate GUIDs from available ranges
- Document your changes

### 2. Asset Creation

Create or modify assets in the appropriate files:

```xml
<ModOp Type="addNextSibling" GUID="100451">
  <Asset>
    <Template>Building</Template>
    <Values>
      <Standard>
        <GUID>1742000XXX</GUID>
        <Name>Your Building Name</Name>
      </Standard>
      <!-- Additional values -->
    </Values>
  </Asset>
</ModOp>
```

### 3. Localization

Add text entries for all new GUIDs:

```xml
<ModOp Type="add" Path="/TextExport/Texts">
  <Text>
    <GUID>1742000XXX</GUID>
    <Text>Your localized text</Text>
  </Text>
</ModOp>
```

### 4. Testing

1. Copy mod to Anno 117 mods folder
2. Launch game and load a save
3. Test your new features
4. Check for errors in game logs
5. Iterate on issues

### 5. Building RDA (Optional)

For distribution, you can package your mod as an RDA file:

1. Use RDA Explorer or FileDBReader
2. Create new RDA archive
3. Add all mod files maintaining directory structure
4. Save as `.rda` file
5. Distribute single file instead of folder structure

## Inheritance Patterns

Anno 117 mods use XML-based inheritance to extend the base game:

### Creating New Assets

```xml
<!-- Base your asset on an existing building -->
<ModOp Type="addNextSibling" GUID="ExistingBuildingGUID">
  <Asset>
    <Template>Building</Template>
    <Values>
      <Standard>
        <GUID>YourNewGUID</GUID>
        <!-- Your modifications -->
      </Standard>
    </Values>
  </Asset>
</ModOp>
```

### Modifying Existing Assets

```xml
<!-- Change a specific property of an existing asset -->
<ModOp Type="merge" GUID="ExistingAssetGUID" Path="/Values/Cost/Costs">
  <Item>
    <Ingredient>1010017</Ingredient>
    <Amount>5000</Amount>
  </Item>
</ModOp>
```

### Removing Elements

```xml
<!-- Remove a specific element from an existing asset -->
<ModOp Type="remove" GUID="ExistingAssetGUID" Path="/Values/Specific/Element" />
```

## Common Asset Templates

- **Building**: Standard structures (houses, production, services)
- **ProductionBuilding**: Factories and workshops
- **PublicService**: Services affecting residents
- **Harbor**: Waterfront structures
- **Ornament**: Decorative elements
- **Product**: Resources and goods
- **UnlockCondition**: Requirements to unlock features
- **UpgradeItem**: Enhancement items for buildings

## Troubleshooting

### Mod Not Loading

1. Check `modinfo.json` syntax (use JSON validator)
2. Verify file paths match exactly (case-sensitive)
3. Check Anno 117 logs in `Documents/Anno 117/logs/`
4. Ensure no GUID conflicts with other mods

### Building Not Appearing

1. Verify GUID is unique and properly assigned
2. Check unlock conditions are met
3. Ensure building category is correctly set
4. Verify all required text entries exist

### Text Not Showing

1. Check GUID matches between assets.xml and text files
2. Verify XML syntax in localization files
3. Ensure correct language folder structure
4. Check for typos in text GUIDs

### UI Issues

1. Verify GUI template references correct GUIDs
2. Check property paths exist and are accessible
3. Ensure GUI modifications don't conflict with base game
4. Test with GUI debug mode if available

## Best Practices

1. **Always use unique GUIDs**: Start from 1742000000 and increment
2. **Document your changes**: Comment complex modifications
3. **Test incrementally**: Make small changes and test frequently
4. **Back up your work**: Use version control (Git recommended)
5. **Follow naming conventions**: Use descriptive, consistent names
6. **Localize everything**: Provide translations for all text
7. **Respect inheritance**: Build on existing assets when possible
8. **Keep it modular**: Separate concerns into different files
9. **Version your releases**: Use semantic versioning (major.minor.patch)
10. **Credit your sources**: If using code/ideas from others, give credit

## Contributing

Contributions are welcome! To contribute:

1. Fork this repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes following the mod structure
4. Update GUID registry if adding new assets
5. Test thoroughly
6. Commit your changes (`git commit -m 'Add amazing feature'`)
7. Push to your branch (`git push origin feature/amazing-feature`)
8. Open a Pull Request

## Resources

### Official Resources
- Anno 117 Official Website
- Anno Union Community Hub
- Official Modding Documentation (when available)

### Community Tools
- **iModYourAnno**: Mod manager and loader
- **RDA Explorer**: For viewing and editing RDA archives
- **FileDBReader**: Alternative RDA tool
- **Anno Designer**: Planning tool for layouts

### Community Sites
- Anno Union Forums
- Reddit: r/anno
- ModDB Anno 117 section
- Nexus Mods Anno 117

## License

This mod template is released under the MIT License. See [LICENSE](LICENSE) file for details.

## Acknowledgments

- Inspired by the Commuter Pier from Anno 1800
- Thanks to the Anno modding community for tools and documentation
- Based on Anno 117's modding framework

## Contact

- **GitHub**: [JustinRudisal/portus-operarum](https://github.com/JustinRudisal/portus-operarum)
- **Issues**: Report bugs and request features via GitHub Issues

## Version History

### 1.0.0 (Initial Release)
- Complete mod template structure
- Sample assets demonstrating inheritance patterns
- English and German localizations
- GUI templates and examples
- Comprehensive documentation

---

**Note**: This is a template/starter mod. All GUIDs, file paths, and asset references are placeholders and examples. When developing your actual mod, replace these with appropriate values for Anno 117's asset system.
