# @lludol/biome-config

My personal Biome configuration for JavaScript/TypeScript projects.

## What is Biome?

[Biome](https://biomejs.dev/) is a fast, modern linter and formatter for JavaScript, TypeScript, JSON, and more. It's a great alternative to ESLint and Prettier.

## Installation

Install this config package as a dev dependency in your project:

```bash
npm install --save-dev @lludol/biome-config @biomejs/biome
```

or with yarn:

```bash
yarn add -D @lludol/biome-config @biomejs/biome
```

or with pnpm:

```bash
pnpm add -D @lludol/biome-config @biomejs/biome
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

- **Formatter**: Enabled with 2-space indentation, 100 character line width
- **Linter**: Enabled with recommended rules
- **Organize Imports**: Enabled
- **JavaScript/TypeScript**:
  - Single quotes
  - Semicolons required
  - ES5 trailing commas

## Publishing

To publish this package to NPM:

```bash
npm login
npm publish --access public
```

## License

MIT
