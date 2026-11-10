# DataMind v3.0 — Master Website Update

## Production connection
- Production frontend defaults to `https://datamind-e5zu.onrender.com`.
- Local dev remains `http://localhost:8000`.
- GitHub Pages Actions now uses the Render URL automatically unless `VITE_API_URL` is explicitly overridden.
- Backend CORS defaults and Render blueprint include `https://anup-prasad1408.github.io` as the frontend origin.

## Source understanding
- Added local extraction of source-grounded important words and important lines.
- Tabular/list sources yield one important line for every extractable record (25 entries remain 25 entries).
- Plain prose uses a transparent heuristic to rank original source sentences; it does not fabricate quotations.
- Important lines and keywords appear in the result and full Markdown export.
- Added CSV and JSON upload. JSON arrays of objects become complete Markdown tables; CSV rows are preserved as pipe-delimited source rows.

## Existing capabilities retained
- Gemini 3.8 Flash is called only from backend Python.
- 12 output formats, document support, complete source coverage, detailed per-item appendix, local fallback, Mermaid previews and inline PNG/SVG export remain included.
- Visual download buttons remain beside their real visual previews; no detached duplicate output panel is added.

## Verification status
- Backend automated tests: run with `pytest -q`.
- Actual supplied AI project PDF upload was checked against multiple output formats using the local API test client, with 25/25 extracted source records preserved.
- Gemini live-key generation and the public Render URL were not reachable from the build runtime and are not claimed as live-verified.
- Frontend full Vite production build must be run after `npm install` on a network-enabled machine.
