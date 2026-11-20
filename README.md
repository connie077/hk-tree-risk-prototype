# Hong Kong Tree Risk Monitoring — Concept Prototype

A single-page interactive prototype of an integrated tree-risk platform for Tai Po District. It aligns three sources that never talk to each other — Highways Department location data (CSDI), the Tree Management Office register, and historical street-view snapshots — and adds a citizen reporting loop, so frontline officers can see one composite risk score per tree and act before typhoon season.

## What is in the prototype

- **Entry screen**: two doors — `Pro version` (desktop workspace for government frontline staff) and `Citizen version` (iPhone app for residents).
- **Pro version**, three modules:
  1. *Integrated risk map* — 34 plotted trees, red ≥ 70 / amber 45–69 / green below; clicking a tree updates the record panel: score breakdown, four aligned sources, and the 2021 → 2024 → 2026 lean trend.
  2. *Priority inspection list* — ten trees ranked by composite score with a recommended action and deadline; filter by 24 hours / dispatched; CSV export.
  3. *Citizen loop* — submitted / in-progress / completed report cards with one-click escalation into the inspection list.
- **Citizen version**: home (typhoon warning, report entry, report status, nearby reports), report form (auto-located position, optional tree number, seven visible issues, at least one photo), confirmation screen, and a status tracker with three states.

Everything lives in one `index.html`: no build step, no dependencies, photos embedded.

## How to run

Open `index.html` in a browser, or:

```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

Deep links via hash: `index.html#pro-map`, `#pro-list`, `#pro-inbox`, `#app-home`, `#app-report`, `#app-track`, `#app-sent`.

## Demo flow (about 90 seconds)

1. Entry screen — three systems hold tree data and none of them match; residents can only phone 1823.
2. Pro → click the red tree: four sources aligned, 82/100, and the lean trend (6° 2021 → 14° 2024 → 24° 2026).
3. Priority list — before a typhoon only ten trees can be reached, so rank them and set deadlines.
4. Citizen version — submit a report live, get report number R-2419, then follow it in *Report status*.
5. Module 03 — one case, one record: residents and frontline see the same progress.

## Notes

- All figures are demonstration data for a class prototype; this is **not** a live government system.
- No brand names appear anywhere in the interface.
