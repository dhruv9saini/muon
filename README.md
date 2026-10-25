# Muon

An infinite canvas web browser by Dhruv Saini. Live web pages sit beside each other on a canvas that you can pan and zoom.


https://github.com/user-attachments/assets/8b154cd6-f317-4f89-8288-2bafcf10ef08


## What I built

The canvas, page-window layout, dragging and resizing, navigation controls, saved workspace state, settings integration and application IPC are implemented here. Electron provides the Chromium browser engine; I did not write a browser engine.

## Source guide

- [src/main.ts](src/main.ts): Electron windows, browser views and app lifecycle.
- [src/preload.ts](src/preload.ts): the renderer's allowed IPC interface.
- [src/renderer](src/renderer): canvas interaction, window management and browser controls.
- [src/config.ts](src/config.ts) and [config.toml](config.toml): configuration.

The project uses Electron, Electron Forge, TypeScript, Tailwind CSS and the [Iosevka](https://github.com/be5invis/Iosevka) typeface.

## Development

Install dependencies using [Bun](https://bun.sh):

```bash
bun install
```

Run the development environment with Electron Forge:

```bash
bun run dev
```

To create production builds:

```bash
bun run build
```

Run ESLint:

```bash
bun run lint
```

## Configuration

Settings are read from `config.toml` in Electron's application path (`app.getAppPath()`), alongside the application source in development. The settings window shows the file location; edit the file directly. Saved workspace state and notes use Electron's separate user-data directory.