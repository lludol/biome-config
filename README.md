# @lludol/biome-config

My personal Biome configuration for JavaScript/TypeScript projects.

## What is Biome?

[Biome](https://biomejs.dev/) is a fast, modern linter and formatter for JavaScript, TypeScript, JSON, and more. It's a great alternative to ESLint and Prettier.

## Installation

Install this config package as a dev dependency in your project:

```bash
npm install --save-dev @lludol/biome-config @biomejs/biome
```

or with pnpm:

```bash
pnpm add -D @lludol/biome-config @biomejs/biome
```

or with bun:

```bash
bun add -d @lludol/biome-config @biomejs/biome
```

## Usage

Create a `biome.json` file in your project root that extends this config:

```json
{
  "extends": ["@lludol/biome-config/biome.json"]
}
```

Or if you need to customize some settings:

```json
{
  "extends": ["@lludol/biome-config/biome.json"],
  "formatter": {
    "lineWidth": 120
  }
}
```

## Scripts

Add these scripts to your `package.json`:

```json
{
  "scripts": {
    "lint": "biome check .",
    "lint:fix": "biome check --write .",
    "format": "biome format --write ."
  }
}
```

## Configuration

This config includes:

- **Formatter**: Enabled with tab indentation (4 spaces), 100 character line width
- **Linter**: Enabled with recommended rules plus custom rules for correctness, style, a11y, security, and performance
- **Organize Imports**: Enabled via assist actions
- **JavaScript/TypeScript**:
  - Double quotes
  - Semicolons required
  - All trailing commas
  - React and Next.js domain support
- **CSS**: Formatter and linter enabled with CSS Modules and Tailwind support

## Publishing

To publish this package to NPM:

```bash
# Login to npm (if not already logged in)
npm login

# Validate the config before publishing (runs automatically via prepublishOnly)
bun run validate

# Publish using bun (validation runs automatically before publish)
bun publish
```

The `prepublishOnly` script automatically validates the Biome configuration before publishing to ensure it's valid.

## License

MIT
