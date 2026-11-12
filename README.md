# OhmZone

Engineering calculation toolboard — a collection of browser-based calculation tools for electrical, mechanical, HVAC, plumbing, structural, fire protection and lighting work.

Live site: https://www.ohmzone.space/

## Tools (17)

Electrical: Cable Tray Fill, Voltage Drop, Plant Load Single-Line, Small Transformer — Cable Sizing & Protection, Motor Circuit — Cable, Protection & Starting Current, Maximum Short-Circuit Current Study, Power Factor Correction — Capacitor Sizing, Conduit Fill Calculator, MV Transformer — Primary Cable Sizing, Battery Bank Sizing, LV Equipment Cable Selection, Harmonic Emission Assessment, Protection Coordination / TCC Study.

Fire alarm (NFPA 72): Battery Sizing, Voltage Drop & NAC Load, Audibility & Line Loss, Detector Spacing & Coverage.

## Notes

- Static site: each tool is a self-contained HTML file with inline CSS/JS. No build step, no backend.
- Standards referenced: CSA C22.1, IEEE 485 / 551 / 242 / C57.109, NFPA 72, NEMA VE1, ICEA P-32-382, CSA C61000-3-6, Hydro-Québec C.25-01.
- Tools are preliminary-design aids, not stamped calculations. Always verify against manufacturer data and the current code edition.
- Deployed on Vercel with automatic deployments from this repository (main branch).

## Changelog

- 2026-11-11: Added global tool search on the homepage (search box + clear button, combines with the category filter, EN/FR).
