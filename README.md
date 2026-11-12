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
- 2026-11-11: Conduit fill — added rigid PVC Schedule 40 / Schedule 80 conduit types (ASTM D1785 IDs; 4 in Sch 40 uses 8091 mm² to match the project calculation book) and corrected PVC outside diameters to IPS values.
- 2026-11-11: Voltage drop — conductor resistance R is now corrected to the selected temperature rating (75 °C table basis; Cu ×1.048 / Al ×1.050 at 90 °C).
- 2026-11-11: Cable tray — corrected the 40% fill note: it is a conservative design guideline, not the NEC rule (NEC 392.22 sets fill by Table 392.22(A) areas for ladder/ventilated trays; 40% applies to solid-bottom trays).
