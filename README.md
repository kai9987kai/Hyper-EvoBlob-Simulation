# Hyper-EvoBlob-Simulation

A **single-file, browser-based simulation** packaged as `index.html`. The repo currently contains **only** that file (HTML/JS) and no additional build tooling, dependencies, or project metadata. :contentReference[oaicite:0]{index=0}

> **Status note:** GitHub currently shows *no description / website / topics* for the repository. :contentReference[oaicite:1]{index=1}  
> The repo history shows a single commit (“Create index.html”). :contentReference[oaicite:2]{index=2}

---

## What this is

**Hyper-EvoBlob-Simulation** is set up as a *run-it-in-the-browser* evolution/simulation playground: an `index.html` that you can open locally (or host with GitHub Pages) to run an interactive visual simulation. :contentReference[oaicite:3]{index=3}

While the implementation details live inside the HTML file, the project name strongly implies an **evolutionary “blob” ecosystem** (typical mechanics: population → evaluation → selection → reproduction/mutation → next generation), rendered in real time in the browser.

---

## Quick start

### Option A — Open directly
1. Download / clone the repo
2. Double-click `index.html` to open it in your browser.

This works for many pure client-side sims, but some browsers restrict file access in `file://` mode.

### Option B — Serve locally (recommended)
From the repo folder:

**Python**
```bash
python -m http.server 8000
