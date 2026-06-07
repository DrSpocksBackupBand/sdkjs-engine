# Office engine bytes (CDN distribution)

Static engine assets served over [jsDelivr](https://www.jsdelivr.com/) for the
companion `sdkjs-runner` web app. This repository holds **only redistributable
runtime bytes** — no build tooling, no server components, no docs.

## Contents

| Path | What | License |
|------|------|---------|
| `v9.3.0.24-1/sdkjs/` | ONLYOFFICE Document Builder client SDK | AGPL-3.0 |
| `v9.3.0.24-1/web-apps/` | ONLYOFFICE editor web apps (document / spreadsheet / presentation / pdf / visio) | AGPL-3.0 |
| `v9.3.0.24-1/fonts/`, `dictionaries/`, … | bundled fonts + spellcheck dictionaries | mixed (see `3rd-Party.txt`) |
| `x2t-1/` | x2t format-conversion WebAssembly | AGPL-3.0 |
| `manifest.json` | per-file size + SHA-256 (integrity / delta updates) | — |

Full license text: `v9.3.0.24-1/LICENSE.txt`; third-party notices:
`v9.3.0.24-1/3rd-Party.txt`. The engine's own in-product attribution is
preserved verbatim.

## Usage

```
https://cdn.jsdelivr.net/gh/DrSpocksBackupBand/sdkjs-engine@v9.3.0.24-1/<path>
```

URLs are immutable per tag, so they cache forever.

### Oversized assets (> 20 MB jsDelivr per-file limit)

`x2t-1/x2t.wasm` and `v9.3.0.24-1/dictionaries/tr_TR/tr_TR.dic` exceed the CDN
per-file limit and are published as **GitHub Release assets** on the matching
tag, fetched from the release download URL rather than the CDN.

## Provenance

Repackaged from a stock ONLYOFFICE DocumentServer `v9.3.0.24-1` extract by
`sdkjs-runner/scripts/pack-engine.mjs` (cruft removed: server components, help
docs, source fonts, build tooling, IE shims, source maps). Capabilities are
left intact.
