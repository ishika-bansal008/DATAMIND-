# DataMind v2.6.0 — Visual export behavior

## What changed

1. Mermaid/flowchart/mind-map/timeline/workflow preview has PNG and SVG buttons in its own toolbar. Those buttons export the exact SVG shown in the preview.
2. Export includes the current preview canvas background, so the saved file no longer becomes transparent or unexpectedly white in dark mode.
3. The separate lower-page `Visual output` panel was removed.
4. Flashcards, infographic cards, presentation cards and comparison tables have compact PNG/SVG controls embedded in the header of the actual visual block.
5. Full card/table exports preserve every record, including records outside the visible scroll area.

## Changed files

- `frontend/src/components/MermaidPreview.jsx`
- `frontend/src/components/ResultPanel.jsx`
- `frontend/src/utils/export.js`
- `frontend/src/styles.css`
- `frontend/package.json`
- `README.md`

## Run checks

```bash
cd backend
python -m pytest -q

cd ../frontend
npm install
npm run build
```

The diagram image itself is exported from the same rendered Mermaid SVG that is visible in the preview; the PNG is rasterized from that SVG. Card/table formats use their complete data to create a full-length PNG/SVG export.
