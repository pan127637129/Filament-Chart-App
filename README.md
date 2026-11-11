# Filament Charts

A small desktop app for managing a personal filament (3D-printing color) library and generating clean listing-style color charts as PNGs.

Built as a **Tauri v2** application (Windows target) with a pure static HTML/JS frontend. No backend, no framework, no build step for the UI itself.

## Product metadata
- **Product name**: Filament Charts
- **Version**: 0.1.0
- **Identifier**: `com.filamentcharts.desktop`
- **Window**: 1200 × 800, resizable, titled “Filament Charts”

## Development

Prerequisites:
- [Rust](https://rustup.rs/)
- [Node.js](https://nodejs.org/) (for Tauri CLI)
- On Windows: Microsoft C++ Build Tools and WebView2 (usually pre-installed on Win10+)

```bash
npm install
npm run tauri dev
```

## Building

```bash
npm run tauri build
```

Produces MSI and NSIS installers in `src-tauri/target/release/bundle/`.

### Icons
Generate icons with:
```bash
npx @tauri-apps/cli icon path/to/source.png
```
Place the resulting icons in `src-tauri/icons/` (or adjust `tauri.conf.json`).

## GitHub Actions
The workflow in `.github/workflows/build-windows.yml` builds Windows installers on push to `main`, tags `v*`, or manual dispatch.

## Data
Library is persisted in `localStorage` under key `filament-chart-library-v1`.

Import/Export uses native dialogs via Tauri plugins.
