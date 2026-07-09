# Contributing to Air1 News

Thank you for helping improve Air1 News. This project is maintained as part of Air1 Quick Tools.

## Adding a News Source

1. Add or update the source definition in `shared/pre-sources.ts`.
2. Add or update the corresponding fetcher in `server/sources/`.
3. Run `pnpm presource` to regenerate `shared/sources.json` and `shared/pinyin.json`.
4. Run the app locally with `pnpm dev` and confirm the source appears in the expected column.

## Development

```sh
corepack enable
pnpm install
pnpm dev
```

Before submitting changes, run the available checks:

```sh
pnpm lint
pnpm typecheck
pnpm test
```

## Style

Keep changes focused, follow the existing TypeScript style, and avoid unrelated refactors.

## License

By contributing, you agree that your contributions are licensed under the project license.
