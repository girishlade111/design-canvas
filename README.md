# Design Canvas — Online Poster & Image Design Tool

A beautiful, full-featured browser-based design editor for posters, marketing creatives, and image editing — built on Canvas. Forked and maintained from the open-source yft-design project.

![Stack](https://img.shields.io/badge/Vue-3-brightgreen) ![Stack](https://img.shields.io/badge/fabric.js-6-blue) ![Stack](https://img.shields.io/badge/Vite-5-purple) ![Stack](https://img.shields.io/badge/TypeScript-5-blue)

## ✨ Features

- **Poster design** — drag-and-drop editor with layers, text, shapes, images, and backgrounds
- **Image editing** — crop, filters, masks, blend modes, and canvas effects
- **Import / export** — export designs as PNG, JPG, SVG, or PDF; import PSD files and restore PDF layouts (Gaoding-style design compatibility)
- **Rich text engine** — multi-style text, fonts, spacing, alignment, text on path
- **Templates & assets** — template gallery, background library, icon/sticker picker
- **History & undo** — full undo/redo timeline
- **Keyboard shortcuts** — pro-editor-style hotkeys throughout
- **Local-first storage** — drafts persist in IndexedDB (Dexie), no account needed

## 🛠 Tech stack

| Layer | Technology |
|---|---|
| UI framework | Vue 3 + TypeScript |
| Canvas engine | fabric.js 6 |
| UI components | Element Plus |
| Build tool | Vite 5 |
| Styling | Tailwind CSS, SCSS |
| Local storage | Dexie (IndexedDB) |
| QR / barcode | beautify-qrcode, jsbarcode |
| Math / utils | lodash-es, number-precision, clipper-lib, delaunator |

## 🚀 Quick start

Prerequisites: Node.js 18+ and npm.

```bash
# install dependencies
npm install --legacy-peer-deps

# start dev server (http://localhost:5174)
npm run dev

# production build (outputs to dist/)
npm run build
```

The built `dist/` folder is fully static and can be served by any static host (GitHub Pages, Cloudflare Pages, nginx).

## 📁 Project structure

```
├── src/                # app source (views, components, hooks, store)
│   ├── views/          # editor pages and panels
│   ├── components/     # reusable UI components
│   └── mocks/          # template / asset mock data
├── build/              # vite plugin + optimization config
├── public/             # static assets copied verbatim
├── index.html          # vite entry
├── vite.config.mts     # build config (relative base "./" — deployable to any subpath)
├── tailwind.config.js
└── tsconfig.json
```

## ⚙️ Notes

- Dev-server proxy (`/api`, `/static`, `/yft-static` in `vite.config.mts`) points at a local backend (`127.0.0.1:8789`); the production build works without it — all editor features run client-side.
- Build target is `es2015` with terser minification (console statements stripped in production).

## 🌐 Live demo

Deployed static build is linked in the repo homepage.

## 🙏 Credits

Based on the open-source [yft-design](https://github.com/dromara/yft-design) project by the Dromara community.

**Built by [Girish Lade](https://ladestack.in)** — part of the [LadeStack](https://ladestack.in) free-tools ecosystem.
