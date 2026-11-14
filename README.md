# OhmZone

Engineering calculation toolboard — a collection of browser-based calculation tools for electrical, mechanical, HVAC, plumbing, structural, fire protection and lighting work.

Live site: https://www.ohmzone.space/

## Tools (20)

Electrical: Cable Tray Fill, Voltage Drop, Plant Load Single-Line, Small Transformer — Cable Sizing & Protection, Motor Circuit — Cable, Protection & Starting Current, Maximum Short-Circuit Current Study, Power Factor Correction — Capacitor Sizing, Conduit Fill Calculator, MV Transformer — Primary Cable Sizing, Battery Bank Sizing, LV Equipment Cable Selection, Harmonic Emission Assessment, Protection Coordination / TCC Study, Grounding System Design, Cable Ampacity — CEC Tables 1–5.

Fire alarm (NFPA 72): Battery Sizing, Voltage Drop & NAC Load, Audibility & Line Loss, Detector Spacing & Coverage.

Fire protection (NFPA 13): Sprinkler Hydraulics (Simplified).

## Notes

- Static site: each tool is a self-contained HTML file with inline CSS/JS. No build step, no backend.
- Standards referenced: CSA C22.1, IEEE 80-2013, IEEE 485 / 551 / 242 / C57.109, NFPA 13, NFPA 72, NEMA VE1, ICEA P-32-382, CSA C61000-3-6, Hydro-Québec C.25-01.
- Tools are preliminary-design aids, not stamped calculations. Always verify against manufacturer data and the current code edition.
- Deployed on Vercel with automatic deployments from this repository (main branch).

## Changelog

- 2026-11-14: New tool — Grounding System Design (GRD·18): IEEE 80-2013 grid resistance (Sverak), mesh/step voltages, tolerable voltages, single-rod Dwight check, m/ft toggle. Verified: 40×30 m grid example Cs=0.7021, Etol=806.59 V, Em=1804.66 V (FAIL), Es=945.90 V (PASS), Rg=1.5458 Ω, GPR=7729.9 V.
- 2026-11-14: New tool — Cable Ampacity (AMP·19): CEC Tables 2/4 with Table 5A temperature and Table 5C bundling corrections, termination-temperature cap (Rule 4-006), Rule 14-104 and 8-104. Verified: 3/0 Cu 75 °C, 40 °C, 6 CCC, 150 A continuous → 140.8 A FAIL; 300 kcmil → 200.64 A PASS. Table 1 free-air 90 °C column only (12 sizes); 60/75 °C columns and Table 3 aluminum free-air values are not included — shown as "— / to be verified", because published sources disagree (see verification log).
- 2026-11-14: New tool — Sprinkler Hydraulics (SPR·20): NFPA 13 simplified — density/area, K-factor head flow, Hazen-Williams friction, riser pressure vs supply, US/SI toggle. Verified: OH1 12×12 ft spacing → 11 heads, 225 gpm, 14.88 psi head pressure, ~25.35 psi riser required.
- 2026-11-14: Cable tray — NEC Table 392.22(A) check implemented (ladder Col. 1 / solid Col. 3, mixed-tray deduction 1.2/1.0 in² per inch of ≥4/0 diameter, single-layer diameter rule). Verified: 30× #4 Cu in 600 mm ladder tray fails NEC (36.93 in² used vs 27.56 allowed) while the 40% guideline passes it — the two checks now disagree visibly, as they should.
- 2026-11-14: Unit toggle — added m/ft length toggle to Voltage Drop and mm/in trade-size toggle to Conduit Fill; short-circuit already had per-run m/ft toggles. Shared `ohmzone-unit` localStorage key is now validated per page so one page's saved value cannot confuse another.
- 2026-11-14: Mobile — homepage filter buttons tightened at ≤680 px; conduit-fill and short-circuit form rows collapse 3→2→1 columns and the title stamp 4→2 columns; voltage drop adds a ≤480 px pass (result stats stack, report padding, full-width export buttons).
- 2026-11-14: Homepage — three new cards (GRD·18, AMP·19, SPR·20) plus a new 💧 Fire Protection category filter; placeholder renumbered to ··21.

- 2026-11-11: Added global tool search on the homepage (search box + clear button, combines with the category filter, EN/FR).
- 2026-11-11: Conduit fill — added rigid PVC Schedule 40 / Schedule 80 conduit types (ASTM D1785 IDs; 4 in Sch 40 uses 8091 mm² to match the project calculation book) and corrected PVC outside diameters to IPS values.
- 2026-11-11: Voltage drop — conductor resistance R is now corrected to the selected temperature rating (75 °C table basis; Cu ×1.048 / Al ×1.050 at 90 °C).
- 2026-11-11: Cable tray — corrected the 40% fill note: it is a conservative design guideline, not the NEC rule (NEC 392.22 sets fill by Table 392.22(A) areas for ladder/ventilated trays; 40% applies to solid-bottom trays).
- 2026-11-11: Battery sizing — temperature correction factors replaced with IEEE 485-1997 Table 1 values (old table was 3–7% low at 0–5 °C and unmarked extrapolation below −3.9 °C); factor floored at 1.00 above 25 °C per IEEE 485-2020 §6.3.2 (no credit for warm electrolyte).
- 2026-11-11: Small transformer — fixed one data error: block E (480 V 1-phase) 5 kVA primary fuse was 8 A, below the 10.42 A rated primary current; corrected to 15 A per CEC 26-254(1)+(3) (125% = 13.02 A, next higher standard rating permitted).
- 2026-11-11: MV transformer — the CSA/NEC standard selector was cosmetic: protection limits were always NEC 450.3(A) (fuse 300%/250%, breaker 600%/400%) even when CSA was selected. CSA now uses CEC Rule 26-250(1) (fuse 150% FLA, breaker 300% FLA, flat); NEC values unchanged; the CSA ledger note now states the correct rule.
