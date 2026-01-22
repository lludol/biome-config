# biome-config-lludol

My personal Biome configuration for JavaScript/TypeScript projects.

## What is Biome?

[Biome](https://biomejs.dev/) is a fast, modern linter and formatter for JavaScript, TypeScript, JSON, and more. It's a great alternative to ESLint and Prettier.

## Installation

Install this config package as a dev dependency in your project:

```bash
npm install --save-dev biome-config-lludol @biomejs/biome
```

or with pnpm:

```bash
pnpm add -D biome-config-lludol @biomejs/biome
```

or with bun:

```bash
bun add -d biome-config-lludol @biomejs/biome
```

## Usage

Create a `biome.json` file in your project root that extends this config:

```json
{
  "extends": ["biome-config-lludol/biome.json"]
}
```

Or if you need to customize some settings:

```json
{
  "extends": ["biome-config-lludol/biome.json"],
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

## Local Testing (Before Publishing)

To test this package locally in other projects before publishing, use bun's link feature:

### Method 1: Using `bun link` (Recommended)

1. **In this package directory** (`biome-config`), create a global link:
   ```bash
   bun link
   ```

2. **In your test project**, link to the package:
   ```bash
   bun link biome-config-lludol
   ```

3. **Install Biome in your test project** (if not already installed):
   ```bash
   bun add -d @biomejs/biome
   ```

4. **Create or update `biome.json`** in your test project:
   ```json
   {
     "extends": ["biome-config-lludol/biome.json"]
   }
   ```

5. **Test it**:
   ```bash
   biome check .
   ```

6. **When done testing**, unlink in your test project:
   ```bash
   bun unlink biome-config-lludol
   ```

### Method 2: Using `file:` protocol

Alternatively, you can install directly from the local path in your test project's `package.json`:

```json
{
  "devDependencies": {
    "biome-config-lludol": "file:../path/to/biome-config",
    "@biomejs/biome": "^2.3.11"
  }
}
```

Then run:
```bash
bun install
```

### Method 3: Using relative path with `bun add`

In your test project:
```bash
bun add -d biome-config-lludol@file:../path/to/biome-config @biomejs/biome
```

**Note**: With `bun link`, changes to this package are immediately available in linked projects without reinstalling. This makes it ideal for active development and testing.

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
