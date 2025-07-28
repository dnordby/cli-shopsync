# Shopsync

A lightweight CLI tool intended to keep premium versioned Shopify themes in sync with updates, without losing, or overwriting theme, style, and functional customizations.

It is primarily intended to be used with **existing** stores, but future enhancements are in the roadmap to consider starting brand new builds using this as a starter.

## Dependencies

- `node` >= `v20.19.0`
- `npm` >= `v10.8.2`
- [Shopify CLI](https://shopify.dev/docs/api/shopify-cli)
- [theme-check](https://github.com/Shopify/theme-check)

## Installation

### Global Installation

```bash
npm i -g @shopsync/cli
```

### Local Installation

```bash
npm install @shopsync/cli
```

## Usage

### With Global Installation

```bash
shopsync init
shopsync connect mystore.myshopify.com 123456789
shopsync sync
```

### With Local Installation

#### Option 1: Using npx (Recommended)

```bash
npx shopsync init
npx shopsync connect mystore.myshopify.com 123456789
npx shopsync sync
```

#### Option 2: Direct execution (Manual setup)

Add this to your project's `package.json`:

```json
{
  "bin": {
    "shopsync": "./node_modules/.bin/shopsync"
  }
}
```

Then run `npm install` to create the symlink, and use:

```bash
shopsync init
shopsync connect mystore.myshopify.com 123456789
shopsync sync
```

## Commands

- `init [directory]` - Initialize shopsync directory
- `connect [store] [themeId]` - Connect to a Shopify store / theme
- `sync` - Sync custom changes to local Shopify theme

---

## Troubleshooting

If `shopsync connect [store] [themeId]` appears to hang, please ensure you are authenticated to Shopify in your terminal. To validate, you can try a command like `shopify theme pull`. If an error is thrown, you are not authenticated and the CLI will not surface commands to log in to Shopify. Please login before continuing.
