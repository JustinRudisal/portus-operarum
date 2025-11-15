# Contributing to Portus Operarum

Thank you for considering contributing to Portus Operarum! This document provides guidelines and information for contributors.

## Code of Conduct

- Be respectful and inclusive
- Provide constructive feedback
- Focus on what's best for the community
- Show empathy towards other contributors

## How to Contribute

### Reporting Bugs

Before creating a bug report:
1. Check existing issues to avoid duplicates
2. Test with only this mod enabled
3. Verify you're using the latest version

When reporting a bug, include:
- Anno 117 version
- Mod version
- Steps to reproduce
- Expected behavior
- Actual behavior
- Screenshots if applicable
- Error messages from logs

### Suggesting Features

Feature suggestions are welcome! Include:
- Clear description of the feature
- Use case / why it's valuable
- How it fits with the mod's theme
- Any implementation ideas

### Pull Requests

1. **Fork the Repository**
   ```bash
   git clone https://github.com/YourUsername/portus-operarum.git
   cd portus-operarum
   ```

2. **Create a Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make Your Changes**
   - Follow the coding standards below
   - Update GUID_REGISTRY.md if adding assets
   - Add localization for new text
   - Test thoroughly

4. **Commit Your Changes**
   ```bash
   git add .
   git commit -m "Add: Brief description of changes"
   ```

   Commit message format:
   - `Add:` for new features
   - `Fix:` for bug fixes
   - `Update:` for modifications
   - `Remove:` for deletions
   - `Docs:` for documentation

5. **Push to Your Fork**
   ```bash
   git push origin feature/your-feature-name
   ```

6. **Create Pull Request**
   - Go to the original repository
   - Click "New Pull Request"
   - Select your branch
   - Fill in the PR template
   - Submit for review

## Coding Standards

### XML Formatting

```xml
<!-- Use consistent indentation (2 spaces) -->
<ModOp Type="addNextSibling" GUID="100451">
  <Asset>
    <Template>Building</Template>
    <Values>
      <Standard>
        <GUID>1742000XXX</GUID>
        <Name>Your Building</Name>
      </Standard>
    </Values>
  </Asset>
</ModOp>
```

### GUID Management

1. **Always check GUID_REGISTRY.md** before adding new GUIDs
2. **Use sequential GUIDs** within appropriate ranges
3. **Update the registry** immediately when allocating GUIDs
4. **Never reuse GUIDs** that were previously active

### File Organization

- Keep related assets in appropriate directories
- One logical feature per file when possible
- Use descriptive filenames
- Maintain consistent naming conventions

### Comments

Add comments for:
- Complex logic
- Non-obvious design decisions
- Placeholder values that need attention
- References to base game assets

```xml
<!-- This references the base game harbor (GUID: 100451) -->
<!-- TODO: Update with actual Anno 117 harbor GUID -->
<ModOp Type="addNextSibling" GUID="100451">
```

### Localization

- Provide translations for all added text
- Minimum: English and German
- Keep strings concise but descriptive
- Use proper grammar and spelling

```xml
<!-- English -->
<Text>
  <GUID>1742000XXX</GUID>
  <Text>Your English text here</Text>
</Text>

<!-- German -->
<Text>
  <GUID>1742000XXX</GUID>
  <Text>Ihr deutscher Text hier</Text>
</Text>
```

## Testing Guidelines

### Before Submitting

Test your changes:
1. Clean install of the mod
2. Verify features work as expected
3. Check for console errors
4. Test with other popular mods (if possible)
5. Verify text displays correctly
6. Check that GUIDs don't conflict

### Test Checklist

- [ ] Mod loads without errors
- [ ] New buildings appear in build menu
- [ ] Building construction works
- [ ] Text is localized in all languages
- [ ] UI elements display correctly
- [ ] No performance issues
- [ ] Backward compatible (if applicable)

## Development Setup

### Prerequisites

- Anno 117 installed
- Text editor (VS Code recommended)
- Git for version control
- XML validator/linter

### Recommended Tools

- **VS Code Extensions:**
  - XML Tools
  - GitLens
  - Spell Checker

- **Anno Modding Tools:**
  - RDA Explorer
  - FileDBReader
  - iModYourAnno

### Project Structure

Familiarize yourself with:
- `data/` - Game data modifications
- `assets/` - Building definitions
- `texts/` - Localization files
- `gui/` - UI templates
- `GUID_REGISTRY.md` - GUID tracking
- `README.md` - Main documentation

## Review Process

Pull requests are reviewed for:
1. **Functionality**: Does it work as intended?
2. **Code Quality**: Is it well-structured and documented?
3. **Compatibility**: Does it maintain backward compatibility?
4. **Standards**: Does it follow coding standards?
5. **Documentation**: Are docs updated appropriately?

### Review Timeline

- Initial review: Within 1 week
- Feedback/revisions: Ongoing discussion
- Merge: When all criteria are met

## Getting Help

Need help? Here are your options:

1. **GitHub Issues**: Ask questions, report problems
2. **Discussions**: General discussion about the mod
3. **Discord**: (If available) Real-time chat
4. **Reddit**: r/anno community

## Attribution

Contributors will be:
- Listed in CONTRIBUTORS.md
- Credited in release notes
- Recognized in the mod description (for major contributions)

## License

By contributing, you agree that your contributions will be licensed under the same license as the project (MIT License).

## Recognition

Significant contributors may receive:
- Mention in mod description
- Special thanks in README
- Co-maintainer status (for ongoing contributors)

## Questions?

Don't hesitate to ask questions! The best way to learn is by doing, and we're here to help.

Thank you for contributing to Portus Operarum! 🚢
