# TYPESCRIPT

Apply these rules to TypeScript source layout, imports, and re-exports.

## Source root and alias

- Use `src` as the default source root.
- Map the `@/*` import alias to `src/*` in `tsconfig.json`.
- Configure the alias in each runtime, test runner, and build tool that needs it.
- Use `@/` for imports between different scopes. Use relative imports within the same scope.

## File extensions

- Import TypeScript modules without file extensions. Use `./config` instead of `./config.js` or `./config.ts`.
- Use paths without file extensions in re-exports as well.
- Keep required extensions for assets, styles, and other non-code files.

## Folder interfaces

- Use `index.ts` as the public interface of a folder.
- Import a folder through its path. Use `@/some-dir` instead of `@/some-dir/index` or `@/some-dir/index.ts`.
