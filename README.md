# @camaro/tsconfig

Shared TypeScript 7 presets with strict type checking and additional code-quality checks.

## Installation

Requires TypeScript 7 (`^7.0.2`).

```bash
npm install --save-dev @camaro/tsconfig typescript@^7.0.2
```

Or using other package managers:

```bash
# pnpm
pnpm add -D @camaro/tsconfig typescript@^7.0.2

# yarn
yarn add -D @camaro/tsconfig typescript@^7.0.2
```

## Usage

Create a `tsconfig.json` in your project root:

```json
{
  "extends": "@camaro/tsconfig/base.json",
  "compilerOptions": {
    "rootDir": "./src",
    "outDir": "./dist"
  },
  "include": ["src"]
}
```

For monorepos using project references, change `extends` to `@camaro/tsconfig/monorepo.json`. It adds `composite: true` to the base configuration.

## Configuration

TypeScript 7 supplies these defaults unless overridden by your project:

| Option | Default |
| --- | --- |
| `strict` | `true` |
| `target` | `ES2025` |
| `module` | `ESNext` |
| `moduleResolution` | `Bundler` |

The base preset additionally enables:

- Checks for unused/unreachable code, return paths, switch fallthrough, overrides, and unchecked indexed access.
- `erasableSyntaxOnly`, `verbatimModuleSyntax`, and `rewriteRelativeImportExtensions`.
- Inline source maps, `lib: ["ESNext"]`, and skipped declaration-file checking (`skipLibCheck`).

See [base.json](./base.json) and [monorepo.json](./monorepo.json) for all options.

For code executed directly by Node.js, set `"module": "NodeNext"` in your project's `compilerOptions`; module resolution follows automatically. Configure runtime-specific `lib` and `types` in your project as needed.

`lib: ["ESNext"]` provides library type declarations. It does not change `target` or add runtime polyfills.

## License

[MIT](LICENSE)

## Author

Dunn

## Links

- [GitHub Repository](https://github.com/camarojs/tsconfig)
- [Report Issues](https://github.com/camarojs/tsconfig/issues)
- [TypeScript Documentation](https://www.typescriptlang.org/tsconfig)
