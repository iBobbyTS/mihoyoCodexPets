---
name: mihoyo-pet-assets
description: Manage this repository's miHoYo-themed Codex pet assets, including game-folder placement, README index updates, hatch-pet run artifacts, chroma-key choices, and final spritesheet QA.
---

# miHoYo Pet Assets

## When To Use

Use this skill together with the installed `hatch-pet` skill whenever creating, repairing, replacing, validating, or organizing a pet asset in this repository.

This repository is an asset collection, not an application codebase. Do not introduce package managers, Docker, build tooling, test frameworks, app scaffolding, or docs structure for normal pet work.

## Repository Layout

- Final pet spritesheets live under the matching game folder:
  - `GenshinImpact/`
  - `HonkaiStarRail/`
  - `ZenlessZoneZero/`
- Keep source generation records in `.pet-runs/<pet-name>/`.
- Treat `output/` and `temp/` as temporary scratch locations unless the user explicitly asks to promote something from them.
- Keep `README.md` as the user-facing index of final pet assets.

## Asset Workflow

1. Identify the target game, region/faction folder if applicable, final display name, and output filename.
2. Use `hatch-pet` for visual generation, row repair, validation, previews, and packaging.
3. Keep all run artifacts under `.pet-runs/<pet-name>/`.
4. Copy or move only the final accepted `spritesheet.webp` into the matching game folder, using the repository's existing naming style.
5. Update `README.md` so the new or changed final asset appears in the correct location.
6. Review the final diff and avoid touching unrelated assets.

## Visual Rules

- Preserve a consistent head-body ratio through a single pet generation.
- Preserve identity-critical features from the source character: silhouette, hair shape, face marks, palette, iconic outfit pieces, and major props.
- Choose a chroma-key background color that does not appear in the target character, outfit, prop, or effects. Use green when it is safe; choose another absent color when green conflicts.
- Prefer simple, readable Codex digital-pet proportions over detailed illustration.
- Avoid detached effects, scenery, text, labels, UI elements, shadows, and frame guides in generated rows unless `hatch-pet` explicitly allows the effect for that state.

## QA Checklist

Before accepting a final pet:

- Open and inspect `.pet-runs/<pet-name>/qa/contact-sheet.png`.
- Check `.pet-runs/<pet-name>/final/validation.json`.
- Check `.pet-runs/<pet-name>/qa/review.json`.
- Inspect relevant preview videos under `.pet-runs/<pet-name>/qa/videos/` when present.
- Confirm the final `.webp` path under the game folder matches `README.md`.
- Confirm no unrelated files were modified or removed.
