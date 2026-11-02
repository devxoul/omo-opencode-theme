# omo-opencode-theme

Theme-only pi package: `themes/*.json`, declared under `pi.themes` in `package.json`. No code, no dependencies.

## Pre-commit checks

Every theme file must be valid JSON:

```sh
for f in themes/*.json; do bun -e "JSON.parse(await Bun.file('$f').text())" || exit 1; done
```

Keep colors aligned with OpenCode's default theme (`packages/tui/src/theme/assets/opencode.json` in sst/opencode). When a token has an OpenCode counterpart, use the same palette color.

## Release

Use the **Release** GitHub Actions workflow (`workflow_dispatch`, see `.github/workflows/release.yml`). It validates the version and theme JSON, bumps `package.json`, publishes to npm with provenance, then commits, tags, and creates a GitHub Release. Tags have no `v` prefix.

```sh
gh workflow run release.yml -f version=X.Y.Z
```

The workflow is the only supported release path. Never run `npm publish` locally.

**Version decision.** Specified version → use as-is. Otherwise default to patch. Color tweaks, new optional tokens, and docs are patches. Minor only for a new theme or a renamed/removed theme. Never bump major unless asked. Never ask the user which to bump.

`package.json` is the single source of truth for the version.
