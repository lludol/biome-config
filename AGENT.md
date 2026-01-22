# Agent Instructions

## README Update Requirements

**CRITICAL**: Whenever you modify `biome.json` or update the Biome version in `package.json`, you MUST update the README.md file to reflect these changes.

### When to Update README

1. **Biome Version Upgrade**: When the `$schema` version in `biome.json` changes or when `peerDependencies.@biomejs/biome` in `package.json` is updated
2. **Config Changes**: When any configuration in `biome.json` is modified (formatter settings, linter rules, JavaScript/TypeScript options, CSS settings, etc.)

### What to Update in README

#### 1. Configuration Section (Lines 64-76)

Update the "Configuration" section to accurately reflect the current state of `biome.json`:

- **Formatter settings**: Check `formatter.indentStyle`, `formatter.indentWidth`, `formatter.lineWidth`
- **Linter rules**: Review `linter.rules` and list all enabled rule categories (correctness, suspicious, style, a11y, security, performance)
- **Organize Imports**: Check if `assist.actions.source.organizeImports` is enabled
- **JavaScript/TypeScript**: Extract from `javascript.formatter`:
  - `quoteStyle` (single/double)
  - `semicolons` (always/never)
  - `trailingCommas` (all/es5/none)
  - Check `linter.domains` for React/Next.js support
- **CSS**: Check `css.formatter.enabled`, `css.linter.enabled`, and `css.parser` options (cssModules, tailwindDirectives)

#### 2. Version References

If the Biome version changes, ensure any version-specific information in the README is updated (though the current README doesn't explicitly mention versions, be aware of this for future updates).

### Update Process

1. Read the current `biome.json` file
2. Read the current `package.json` to check the Biome version requirement
3. Compare with the "Configuration" section in `README.md`
4. Update the README to match the actual configuration
5. Ensure the description is accurate and reflects all enabled features

### Example Checklist

When updating the README Configuration section, verify:
- [ ] Formatter indentation style and width match `biome.json`
- [ ] Line width matches `formatter.lineWidth`
- [ ] All enabled linter rule categories are listed
- [ ] JavaScript formatter options (quotes, semicolons, trailing commas) match
- [ ] Domain support (React/Next.js) is mentioned if present
- [ ] CSS features are accurately described
- [ ] Any new features added to the config are documented

### Important Notes

- The README should only show installation instructions for **npm, pnpm, and bun** (no yarn)
- The publishing section should reference `bun publish` and the validation process
- Keep the Configuration section concise but comprehensive
- Always verify the README matches the actual `biome.json` configuration after any changes
