# Building Your Mod for Distribution

This guide explains how to package and distribute your Portus Operarum mod.

## Distribution Formats

Anno 117 mods can be distributed in two formats:

### 1. Folder Structure (Development/Easy Testing)

**Pros:**
- Easy to modify and test
- No special tools required
- Great for development

**Cons:**
- Multiple files to manage
- Users must maintain folder structure

**How to distribute:**
1. Zip the entire mod folder
2. Include clear installation instructions
3. Maintain directory structure in the zip

### 2. RDA Archive (Production/Release)

**Pros:**
- Single file distribution
- Professional appearance
- Slightly faster loading

**Cons:**
- Requires RDA tools
- Harder to modify for users
- One extra build step

**How to create:**
See "Building RDA Archives" section below

## Pre-Release Checklist

Before releasing your mod:

- [ ] Test all features thoroughly
- [ ] Verify all text is localized
- [ ] Check for GUID conflicts
- [ ] Update version number in modinfo.json
- [ ] Write/update CHANGELOG
- [ ] Test with a clean install
- [ ] Test compatibility with popular mods
- [ ] Spell-check all documentation
- [ ] Create screenshots/preview images
- [ ] Test on different game versions (if applicable)

## Building RDA Archives

### Using RDA Explorer (Windows)

1. **Download RDA Explorer**
   - Available from Anno modding communities
   - Extract to a convenient location

2. **Create RDA Archive**
   ```
   - Launch RDA Explorer
   - File → New → RDA
   - Select RDA version (use latest for Anno 117)
   - Add your mod files maintaining structure
   - Save as portus_operarum_v1.0.0.rda
   ```

3. **Verify Archive**
   - Reopen the .rda file
   - Check all files are present
   - Verify folder structure is correct

### Using FileDBReader (Command Line)

1. **Download FileDBReader**
   - Available from Anno modding communities
   - Command-line tool for RDA management

2. **Create Archive**
   ```bash
   FileDBReader.exe create portus_operarum_v1.0.0.rda /path/to/mod/folder
   ```

3. **Verify Archive**
   ```bash
   FileDBReader.exe list portus_operarum_v1.0.0.rda
   ```

## Version Numbering

Use semantic versioning (MAJOR.MINOR.PATCH):

- **MAJOR**: Breaking changes, incompatible with previous saves
- **MINOR**: New features, backward compatible
- **PATCH**: Bug fixes, backward compatible

Examples:
- `1.0.0`: Initial release
- `1.1.0`: Added new building
- `1.1.1`: Fixed text typo
- `2.0.0`: Complete overhaul

## Creating a Release

### GitHub Releases (Recommended)

1. **Prepare Release**
   ```bash
   git tag -a v1.0.0 -m "Release version 1.0.0"
   git push origin v1.0.0
   ```

2. **Create GitHub Release**
   - Go to your repository
   - Click "Releases" → "Create a new release"
   - Select your tag (v1.0.0)
   - Write release notes
   - Attach files (.zip and/or .rda)
   - Publish release

3. **Release Notes Template**
   ```markdown
   ## Version 1.0.0
   
   ### New Features
   - Added Portus Operarum wharf building
   - Implemented worker ferry system
   
   ### Changes
   - Updated building costs
   
   ### Bug Fixes
   - Fixed localization issues
   
   ### Known Issues
   - None at this time
   
   ### Installation
   1. Download portus_operarum_v1.0.0.zip
   2. Extract to Documents/Anno 117/mods/
   3. Launch game
   ```

### ModDB / Nexus Mods

1. **Create Account** on your chosen platform
2. **Create Mod Page**
   - Upload preview images/screenshots
   - Write compelling description
   - Add categories and tags
   - Link to GitHub for support

3. **Upload Files**
   - Upload both .zip and .rda versions
   - Mark appropriate version
   - Add changelog

4. **Maintain Mod Page**
   - Respond to comments
   - Update for game patches
   - Post news about updates

## Packaging Checklist

Your release package should include:

```
portus_operarum_v1.0.0.zip
├── portus-operarum/           # Mod folder
│   ├── modinfo.json
│   ├── data/
│   ├── assets/
│   ├── texts/
│   ├── gui/
│   └── README.md
├── CHANGELOG.md               # Version history
├── INSTALLATION.md            # Installation guide
└── LICENSE                    # Your license file
```

## Testing Your Release

Before publishing:

1. **Clean Install Test**
   - Remove all traces of development version
   - Install from release package
   - Test all features

2. **Compatibility Test**
   - Test with vanilla game
   - Test with popular mods
   - Document any conflicts

3. **Performance Test**
   - Play for extended session
   - Check for memory leaks
   - Monitor game performance

## Updating Your Mod

When releasing updates:

1. **Increment Version**
   - Update modinfo.json version
   - Create new Git tag
   - Update CHANGELOG.md

2. **Maintain Backward Compatibility**
   - Don't remove or change existing GUIDs
   - Add new features alongside old ones
   - Provide migration path if needed

3. **Document Changes**
   - Clear changelog
   - Update README if needed
   - Note any breaking changes

## Marketing Your Mod

1. **Create Good Screenshots**
   - Show buildings in-game
   - Demonstrate features
   - Use good lighting/angles

2. **Write Clear Description**
   - Explain what your mod does
   - List key features
   - Show installation steps

3. **Engage Community**
   - Post on Reddit (r/anno)
   - Share on Anno Union
   - Respond to feedback

4. **Create Video (Optional)**
   - Showcase features
   - Installation tutorial
   - Gameplay demonstration

## Licensing

Choose an appropriate license:

- **MIT**: Very permissive, allows commercial use
- **GPL**: Requires derivatives to be open source
- **CC BY-NC-SA**: Attribution required, non-commercial
- **All Rights Reserved**: Most restrictive

Include LICENSE file in your release.

## Support and Maintenance

1. **Monitor Issues**
   - Check GitHub Issues regularly
   - Respond to bug reports
   - Accept pull requests

2. **Update for Game Patches**
   - Test after Anno 117 updates
   - Fix compatibility issues
   - Release patches as needed

3. **Communicate**
   - Announce updates
   - Be transparent about development
   - Set realistic expectations

## Common Distribution Mistakes

Avoid these common errors:

- ❌ Not testing release package
- ❌ Forgetting to update version numbers
- ❌ Including development files (.git, node_modules)
- ❌ Unclear installation instructions
- ❌ No changelog
- ❌ Breaking backward compatibility without warning
- ❌ Not responding to users
- ❌ Abandoning mod without notice

## Quick Build Script Example

Create a `build.sh` script (Linux/Mac) or `build.bat` (Windows):

```bash
#!/bin/bash
# Build script for Portus Operarum

VERSION="1.0.0"
MOD_NAME="portus_operarum"

echo "Building ${MOD_NAME} v${VERSION}..."

# Create build directory
mkdir -p build

# Create release zip
zip -r "build/${MOD_NAME}_v${VERSION}.zip" \
  modinfo.json \
  data/ \
  assets/ \
  texts/ \
  gui/ \
  README.md \
  GUID_REGISTRY.md \
  LICENSE \
  -x "*.git*" "*.DS_Store" "*.tmp"

echo "Build complete: build/${MOD_NAME}_v${VERSION}.zip"
```

Make executable:
```bash
chmod +x build.sh
```

Run:
```bash
./build.sh
```

## Conclusion

Distribution is an important part of modding. Take time to:
- Package properly
- Test thoroughly
- Document clearly
- Support your users

Your effort will result in a better experience for everyone!
