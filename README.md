# Asset360 Inspect

A mobile-first, standalone hotel property inspection app for owner-side asset management.

## Features
- 10 inspection areas and 79 checkpoints spanning FOH, guestrooms, F&B, BOH, building envelope, roof, mechanical systems, life safety and management practices.
- Separate assessments for **physical condition** (Excellent / Good / Fair / Poor / Critical) and **quality of care** (Proactive / Adequate / Reactive / Neglected).
- Per-checkpoint narrative, management explanation, recommended action, priority, cost category, owner, due date and compressed photo evidence.
- Auto-save in browser IndexedDB, with multiple saved inspections.
- Owner action register, inspection coverage, summary distributions.
- Download CSVs for observations and actions, plus a **full JSON backup including photos**; restore JSON backups.
- No server, tracking, libraries, or API keys.

## Publish on GitHub Pages
1. Create a GitHub repository, such as `asset360-inspect`.
2. Add `index.html` and this `README.md` in the repository root. Commit changes.
3. Visit repository **Settings → Pages**, select **Deploy from a branch**, select branch `main` and `/ (root)`, then save.
4. Once deployed, open `https://YOUR-USERNAME.github.io/asset360-inspect/` on your phone; optionally **Add to Home Screen**.

## Important storage / confidentiality notes
- All inspection data stays in **the browser on the device where it was entered**. GitHub Pages only serves the application code. There is NO login, sync, or server-side backup.
- Download full JSON backups regularly, especially after each site visit, and store them securely. CSV exports do not contain photo files.
- Do not commit exported inspections, hotel photos, private data, or other confidential work product to the public repo.
- Clearing browser site data, using private mode, changing devices, or deleting the browser can erase unsaved or unexported records.
- Photo storage consumes device capacity. Photos are resized locally to max 1600px and JPEG quality 77%.
- This is a qualitative owner walkthrough, not an engineering certification, regulatory inspection, formal ADA compliance assessment, or replacement for licensed specialists. Do not enter restricted areas or climb roofs without safe access/authorization.

## Data schema
Each inspection has its own ID, date, property, inspector, inspection type and narrative. Ratings keyed by `categoryIndex-checkpointIndex` contain condition, care, N/A, observations, action, response, priority, cost category, owner, due date, and images. CSV exports contain one row per reviewed or flagged checkpoint, preserving property/inspection metadata; a future Asset360 ingestion layer can normalize these into property, inspection, area, checkpoint, finding, and action tables.
