# @camaro/tsconfig

A shareable TypeScript configuration with strict type checking and modern compiler options.

## Features

- ✅ Strict type checking configuration
- 🔒 All strict mode options enabled
- 🚀 Latest ESNext target and module system
- 📦 Node.js `nodenext` module resolution support
- 🏗️ Monorepo-specific configuration included
- 🔄 ESM interoperability out of the box

## Installation

```bash
npm install --save-dev @camaro/tsconfig
```

Or using other package managers:

```bash
# pnpm
pnpm add -D @camaro/tsconfig

# yarn
yarn add -D @camaro/tsconfig
```

## Usage

### Base Configuration

Create a `tsconfig.json` file in your project root and extend the base configuration:

```json
{
  "extends": "@camaro/tsconfig/base.json",
  "compilerOptions": {
    "outDir": "./dist"
  },
  "include": ["src"]
}
```

### Monorepo Configuration

If you're using a monorepo (such as pnpm workspaces, yarn workspaces, or lerna), use the dedicated monorepo configuration:

```json
{
  "extends": "@camaro/tsconfig/monorepo.json",
  "compilerOptions": {
    "outDir": "./dist"
  },
  "include": ["src"]
}
```

## Configuration Details

### base.json

The base configuration includes the following strict compiler options:

#### Type Checking
- `strict: true` - Enable all strict type checking options
- `noImplicitReturns: true` - Ensure all code paths in functions return a value
- `noFallthroughCasesInSwitch: true` - Prevent fallthrough errors in switch statements
- `noUnusedLocals: true` - Report unused local variables
- `noUnusedParameters: true` - Report unused parameters
- `noUncheckedIndexedAccess: true` - Add undefined checks for index access
- `noImplicitOverride: true` - Ensure overriding members use the override modifier
- `allowUnreachableCode: false` - Disallow unreachable code
- `allowUnusedLabels: false` - Disallow unused labels

#### Module System
- `module: "nodenext"` - Use Node.js ESM and CommonJS support
- `moduleResolution: "nodenext"` - Node.js module resolution strategy

#### Emit Options
- `inlineSourceMap: true` - Generate inline source maps

#### Interoperability
- `esModuleInterop: true` - Enable ES module interoperability
- `forceConsistentCasingInFileNames: true` - Enforce consistent file name casing

#### Language and Environment
- `target: "ESNext"` - Compile to the latest ECMAScript standard
- `lib: ["ESNext"]` - Use the latest standard library type definitions

#### Other
- `skipLibCheck: true` - Skip type checking of declaration files for better performance

### monorepo.json

Extends `base.json` with additional options:
- `composite: true` - Enable project references and incremental compilation, suitable for monorepo scenarios

## Why Use This Configuration?

1. **Strictness**: Enables all TypeScript strict checking options to catch potential issues during development
2. **Modern**: Uses ESNext target to support the latest JavaScript features
3. **Node.js Friendly**: Uses `nodenext` module system for perfect Node.js ESM support
4. **Optimized Developer Experience**: Configured with reasonable error detection and code hints
5. **Monorepo Support**: Provides dedicated monorepo configuration with project reference support

## License

[MIT](LICENSE)

## Author

Dunn

## Links

- [GitHub Repository](https://github.com/camarojs/tsconfig)
- [Report Issues](https://github.com/camarojs/tsconfig/issues)
- [TypeScript Documentation](https://www.typescriptlang.org/tsconfig)
