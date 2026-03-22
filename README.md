# CAD Viewer for Google Drive™

**CAD Viewer** is a free web application that lets you open and view **2D CAD drawings** (DWG, DXF) and **3D models** (glTF, GLB, OBJ, FBX, STL) directly from **Google Drive™** in the browser — no software installation required.

Live app: [https://cad.thingraph.site/](https://cad.thingraph.site/)
Install from Google Workspace Marketplace: [CAD Viewer – Google Workspace Marketplace](https://workspace.google.com/marketplace/app/dwg_viewer/641533811831)

---

## Supported File Formats

| Format | Description |
|--------|-------------|
| **DWG** | AutoCAD Drawing — the most widely used 2D CAD format |
| **DXF** | Drawing Exchange Format — open CAD interchange format |
| **glTF** | GL Transmission Format (JSON + external .bin / textures) |
| **GLB** | Binary glTF — single-file, self-contained 3D model |
| **OBJ** | Wavefront Object — widely supported 3D mesh format |
| **FBX** | Autodesk Filmbox — common in animation and game pipelines |
| **STL** | Stereolithography — used in 3D printing and CAD |

---

## Features

- **High-performance 2D WebGL rendering** — DWG/DXF files are parsed and rendered entirely in the browser using WebGL (Three.js), no server-side conversion needed
- **Full 3D model viewer** — glTF, GLB, OBJ, FBX, STL with orbit, pan, zoom
- **Layer management** — show/hide DWG/DXF layers, manage layer visibility
- **Layout switching** — switch between model space and paper space layouts in multi-layout DWG/DXF files
- **Measurement tools** — distance, area, angle, coordinate measurements with object snapping (osnap)
- **Markup & annotation** — arrows, rectangles, circles, text annotations with undo/redo
- **Screenshot** — export high-quality PNG images of the current view
- **Section plane** — clip 3D models with interactive section planes
- **Tree view** — browse and select model hierarchy
- **Skybox & ground shadow** — realistic environment for 3D models
- **Settings panel** — customize background, rendering quality, and more
- **Google Drive™ integration** — open files via "Open with" directly from Google Drive™ without downloading

---

## Powered by x-viewer SDK

CAD Viewer is built on top of the **`@x-viewer/core`** and **`@x-viewer/plugins`** JavaScript SDK — a high-performance WebGL-based 2D and 3D viewer engine for the web.

The 2D DWG/DXF viewer stack is powered by **[cad-viewer](https://github.com/mlightcad/cad-viewer)** (mlightcad), an open-source browser-based DXF/DWG viewer and editor.


### About @x-viewer/core

`@x-viewer/core` is a TypeScript/JavaScript SDK for building CAD and 3D model viewer applications in the browser. It provides:

- **`Viewer2d`** — a WebGL-based 2D viewer for DWG and DXF files, built on Three.js
- **`Viewer3d`** — a WebGL-based 3D viewer for glTF, GLB, OBJ, FBX, STL, built on Three.js

Key capabilities of the SDK:

- Parse and render DWG/DXF entirely client-side (no backend/server required)
- Support for AutoCAD entity types: LINE, ARC, CIRCLE, POLYLINE, LWPOLYLINE, SPLINE, HATCH, TEXT, MTEXT, INSERT, DIMENSION, LEADER, MLEADER, ELLIPSE, SOLID, and more
- Layer control, layout switching, osnap, distance/area/angle measurements
- Markups, hotpoints, comparison mode, undo/redo
- Full TypeScript support with comprehensive type definitions
- Modular plugin architecture via `@x-viewer/plugins`

### Install @x-viewer/core

```bash
npm install @x-viewer/core @x-viewer/plugins
# or
pnpm add @x-viewer/core @x-viewer/plugins
```

### Quick Start — Viewer2d (DWG/DXF)

```typescript
import { Viewer2d } from '@x-viewer/core'

const viewer = new Viewer2d({ containerId: 'myCanvas' })
await viewer.setFont(['hztxt.shx', 'simplex.shx'])
await viewer.loadModel({ modelId: 'drawing', src: 'path/to/file.dwg' })
viewer.goToHomeView()
```

### Quick Start — Viewer3d (glTF/GLB/OBJ/FBX/STL)

```typescript
import { Viewer3d } from '@x-viewer/core'

const viewer = new Viewer3d({ containerId: 'myCanvas' })
await viewer.loadModel({ modelId: 'model', src: 'path/to/model.glb' })
```

### Related Packages

| Package | Description |
|---------|-------------|
| `@x-viewer/core` | Core viewer engine — `Viewer2d` and `Viewer3d` |
| `@x-viewer/plugins` | Plugin modules: toolbar, measurements, markups, tree view, skybox, section, screenshots, etc. |

### Examples & Demos

- SDK examples repository: [github.com/thingraph/dwg-viewer-example](https://github.com/thingraph/dwg-viewer-example)
- Live SDK demos: [dwg.thingraph.site](https://dwg.thingraph.site/)

---

## How to Use CAD Viewer with Google Drive™

1. Install **CAD Viewer** from the [Google Workspace Marketplace](https://workspace.google.com/marketplace/app/dwg_viewer/641533811831)
2. Open [Google Drive™](https://drive.google.com) in your browser
3. Right-click a DWG, DXF, glTF, GLB, OBJ, FBX, or STL file
4. Choose **Open with → CAD Viewer**
5. Sign in with Google if prompted — the app only accesses the specific file you open
6. Use the toolbar to zoom, pan, measure, annotate, or export screenshots

You can also open local files directly at [cad.thingraph.site/open](https://cad.thingraph.site/open) without connecting Google Drive™.

---

## Privacy & Data

- The app requests only `drive.file` and `drive.install` OAuth scopes
- `drive.file` — read access to files you explicitly open via "Open with"
- `drive.install` — allows the app to appear in the Google Drive™ "Open with" menu
- File content is processed entirely in your browser — no files are uploaded to our servers
- We do not store, index, or share your files or file metadata

---

## Contact

- Email: thingraph@outlook.com
- GitHub: [github.com/thingraph/dwg-viewer-example](https://github.com/thingraph/dwg-viewer-example)

---

*Google Drive™ is a trademark of Google LLC. CAD Viewer is not affiliated with or endorsed by Google LLC*
