# Prototype Studio — handoff

Continue developing this existing app; do not rebuild it from scratch.

## Files
index.html, style.css, app.js, and three.js (bundled Three.js r170). Keep all four in the same folder. No API keys, package installation, or build step required. Serve the folder with a static web server, for example `python -m http.server 8000`, then open http://localhost:8000. Opening index.html directly as a file may fail because it imports JavaScript modules. The files can also be uploaded to static hosting.

## Purpose
A kid-friendly 3D planning tool for Making Makers, eventually connected to Musical Makers. Primary audience grades 1–3, full-size iPad landscape and desktop. Students arrange actual building materials at fixed sizes. No resizing or physics simulation.

## Current features and rules
- Limited challenge: 4 straws (20 cm), 1 cardboard (20 x 15 cm), 4 craft sticks (11.5 cm). Remaining stock shown.
- Move, lift with pine-tree handle, CW/CCW rotation in 15-degree steps around fixed world axes.
- Reset selected piece to original position/orientation; separate Drop to table.
- Duplicate whole pieces consumes stock. Cut pieces cannot be duplicated.
- Flat cutting mat divides straws/sticks into pieces, preserving all offcuts. Cardboard cutting not implemented.
- Cuts and confirmed discards are final for the attempt, clearing earlier undo history. Discard does not replenish inventory.
- Placement/rotation undo, saved picture export, local browser autosave.
- Mouse: left-drag pieces, right-drag orbit (vertical reversed), wheel zoom, middle-drag pan. Shift-drag also pans.
- Touch: one finger moves pieces/orbits empty space, two fingers pan and pinch zoom. Current touch directions were tuned with Andy; preserve them.
- Center button restores camera. Small-screen warning.
- Software fallback renderer when WebGL is unavailable.

## Latest change and verification
This export includes the latest page-pinch suppression change: CSS touch-action plus Safari gesture/touch handlers, keeping custom tray pinch handling. Syntax checked; actual iPad behavior still needs testing. This last change was packaged but not confirmed deployed in the original thread.
Earlier iPad straw-button issue received direct touch tap handling and an added/error toast; do not assume the device-specific issue is fully resolved without Andy testing.

## Persistence and limitations
Challenge data uses localStorage key mm-material-challenge-v1. Previous free-build data remains in mm-prototype-v1 but is not loaded in challenge mode. Existing pieces before reset tracking used their then-current position as the reset origin. Saved student scenes are browser-local and are NOT in this ZIP. No teacher/session controls or new-attempt button yet. Inventory is a browser-local classroom prototype, not tamper-resistant enforcement.

## Continuing in another chat
Read all three application source files before editing. Make focused changes and return updated downloadable files. Avoid changing already-tuned mouse/touch directions. Three.js is bundled, so the app has no CDN runtime dependency.
