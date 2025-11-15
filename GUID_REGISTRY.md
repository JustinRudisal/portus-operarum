# GUID Registry for Portus Operarum

This document tracks all GUIDs (Global Unique Identifiers) used in this mod to prevent conflicts and maintain organization.

## GUID Allocation Strategy

- **Base Range**: 1742000000 - 1742999999
- **Increment**: Always increment by 1 for new assets
- **Check**: Before adding a GUID, verify it's not already in use
- **Document**: Always update this registry when adding new assets

## Registered GUIDs

### Buildings (1742000001-1742000099)

| GUID | Asset Name | Type | File | Status |
|------|------------|------|------|--------|
| 1742000001 | Portus Operarum Wharf | Harbor Building | data/config/export/main/asset/assets.xml | Active |
| 1742000002 | Unlock Portus Operarum | UnlockCondition | data/config/export/main/asset/assets.xml | Active |
| 1742000010 | Worker Ferry | Production Building | assets/buildings/building_definitions.xml | Active |
| 1742000011 | Commuter Station | Public Service | assets/buildings/building_definitions.xml | Active |
| 1742000012 | Portus Operarum Sign | Ornament | assets/buildings/building_definitions.xml | Active |
| 1742000013 | Enhanced Ferry Upgrade | Upgrade Item | assets/buildings/building_definitions.xml | Active |

### Products and Resources (1742000020-1742000049)

| GUID | Asset Name | Type | File | Status |
|------|------------|------|------|--------|
| 1742000020 | Workers (Resource) | Product | TBD | Placeholder |
| 1742000021 | Transported Workers | Product | TBD | Placeholder |

### UI Text Elements (1742000100-1742000199)

| GUID | Text Content | Purpose | Files | Status |
|------|--------------|---------|-------|--------|
| 1742000100 | "Workforce Transportation" | UI Section Header | texts/*/portus_operarum_*.xml | Active |
| 1742000101 | "Connected Islands" | UI Label | texts/*/portus_operarum_*.xml | Active |
| 1742000102 | "Active Commuters" | UI Label | texts/*/portus_operarum_*.xml | Active |

### Status Messages (1742000200-1742000299)

| GUID | Text Content | Purpose | Files | Status |
|------|--------------|---------|-------|--------|
| 1742000200 | "Portus Operarum operational" | Status Message | texts/*/portus_operarum_*.xml | Active |
| 1742000201 | "No connection to other islands" | Status Message | texts/*/portus_operarum_*.xml | Active |
| 1742000202 | "Workers commuting" | Status Message | texts/*/portus_operarum_*.xml | Active |

### Effects and Modifiers (1742000300-1742000399)

| GUID | Asset Name | Type | File | Status |
|------|------------|------|------|--------|
| 1742000300-1742000399 | Reserved for future effects | - | - | Reserved |

### Icons and UI Assets (1742000400-1742000499)

| GUID | Asset Name | Type | File | Status |
|------|------------|------|------|--------|
| 1742000400-1742000499 | Reserved for UI assets | - | - | Reserved |

## Available Ranges

The following GUID ranges are available for expansion:

- **1742000050-1742000099**: Available for additional buildings
- **1742000300-1742000399**: Available for effects and modifiers
- **1742000400-1742000499**: Available for UI assets
- **1742000500-1742000999**: Available for general expansion

## Adding New GUIDs

When adding a new asset:

1. Choose the next available GUID in the appropriate range
2. Add an entry to this document with:
   - GUID number
   - Asset name
   - Asset type
   - File location
   - Status (Active/Placeholder/Reserved)
3. Use the GUID in your asset definition
4. Add corresponding localization entries
5. Commit changes to this registry

## GUID Conflicts

If you encounter a GUID conflict:

1. Check this registry for the conflicting GUID
2. Choose a new, unused GUID
3. Update all references to the old GUID
4. Update this registry
5. Test thoroughly

## External GUID References

When referencing base game assets, use these common GUIDs (examples):

- **100451**: Generic harbor building (placeholder)
- **1010017**: Gold
- **1010196**: Wood
- **1010205**: Stone
- **1010343**: Example population tier
- **214935**: Generic harbor ambience sound

**Note**: These are placeholder examples. Actual Anno 117 GUIDs should be referenced from official documentation or extracted from game files.

## Maintenance

- Review this registry monthly
- Remove unused GUIDs marked as "Placeholder" after 3 months
- Consolidate ranges if fragmentation occurs
- Keep this document synchronized with actual asset files

## Version History

- **1.0.0**: Initial GUID registry with base allocations
