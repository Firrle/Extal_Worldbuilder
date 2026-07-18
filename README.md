# Extal World Builder

<p align="center">
  <img src="docs/github/extal.png" alt="Extal World Builder" width="100%">
</p>

<p align="center">
  A desktop worldbuilding studio for writers, storytellers, and long-form fiction projects.
</p>

<p align="center">
  Draft chapters and scenes, build a living encyclopedia, track timeline events, manage characters, and pin story details directly onto maps.
</p>

## What The App Does

Extal World Builder is built around one idea: your writing, lore, characters, places, and history should all stay connected while you work.

Inside the app, the major tabs work together:

- `Draft` for chapter and scene writing
- `World` for encyclopedia-style topic building
- `Characters` for profile and relationship tracking
- `Timeline` for event ordering and continuity
- `Maps` for visual location building and marker linking

## App Preview

### Draft

Write scenes in a focused editor with a chapter-and-scene binder on the left and project metadata on the right.

![Draft Tab](https://github.com/Firrle/extal/blob/main/docs/github/docs/github/draft-tab.png)

### World

Build a connected reference system for lore, metaphysics, factions, artifacts, regions, and setting structure.

![World Tab](docs/github/world-tab.png)

### Characters

Track character identity, biography, motivations, background, and where each person is referenced across the project.

![Characters Tab](docs/github/characters-tab.png)

### Timeline

Keep major events ordered visually so story logic and historical continuity are easier to manage.

![Timeline Tab](docs/github/timeline-tab.png)

### Maps

Place markers, connect locations to topics and events, and use built-in measurement tools to support travel and world scale.

![Maps Tab](docs/github/maps-tab.png)

![Map Measurement Tools](docs/github/maps-measurement.png)

![Map Roads, Borders, and Terrain Measuring](docs/github/map_terrain_border.png)

## Why It Feels Different

- The writing side and worldbuilding side live in the same app instead of being split across separate tools.
- References are meant to stay navigable, not buried in loose notes.
- The interface is designed for story continuity, not just text storage.
- TinyMCE powers the core editing experience across the app.

## Core Stack

- `Electron`
- `TinyMCE`
- frontend UI and theme system in `frontend/`
- local helper tooling in `backend/`
- optional Piper TTS support in `tts/`

## Project Structure

- `main.js` - Electron main process
- `preload.js` - Electron preload bridge
- `frontend/` - UI, editor integration, assets, maps, and themes
- `backend/` - Python helpers and local tooling
- `mcp/` - MCP server integration for local tools like LM Studio
- `scripts/` - build and utility scripts
- `themes/` - theme definitions

## LM Studio MCP

Extal now includes a local MCP server so `LM Studio` can query a saved vault directly with your own local model.

- Server entry: `mcp/extal-mcp-server.js`
- Setup guide: [readme files/LM_STUDIO_MCP_SETUP.md](readme%20files/LM_STUDIO_MCP_SETUP.md)

## Run In Development

Install dependencies:

```bash
npm install
```

Start the app:

```bash
npm start
```

## Build

```bash
npm run dist
npm run dist:linux
npm run dist:win
npm run dist:mac
```

For Linux AppImage builds, this repo may use a local writable cache setup during packaging.

## Repository Notes

Large generated output and bundled runtime payloads are intentionally kept out of Git where possible, including:

- `dist/`
- `node_modules/`
- `backend/python/`
- large wheel payloads
- large Piper model binaries
