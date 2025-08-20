# H100 Electrical Full Build Package â€” Review Notes (R1.4c)

Date: 2025-08-16  
PR Type: Documentation package review (no functional code changes)

---

## Scope
- DC schematic: `diagrams/dc_schematic.drawio` (+ SVG/PNG + A3/A2 PDFs)
- AC schematic: `diagrams/ac_schematic.drawio` (+ SVG/PNG + A3/A2 PDFs)
- Installation guide: `docs/installation.md`
- Safety notes: `docs/safety.md`
- Bill of Materials: `bom/bom.csv`

## Key Specs Confirmed
- Batteries: **2 Ã— Valence U27-12**
- External BMS: **JK BMS** (controls **TE EV200** contactor)
- Shunt: **Victron SmartShunt 500 A**
- PV: **2 Ã— 200 W** panels in series â†’ roof gland â†’ PV isolator â†’ **Victron SmartSolar 100/30**
- DC-DC: **Victron Orion-Tr Smart 12/12-30 A** (isolated)
- Inverter: **Victron Phoenix Inverter Smart 12/1200**
- 12 V Distribution: **Blue Sea 5029**; bus bars **Blue Sea 2104/2105**

## What to Review
- Schematic readability (orthogonal routing; labels use white pill style)
- Contents block (brand/model lines) and PV configuration (2 Ã— 200 W series)
- Fuse sizes and wire gauges noted near paths (2/0 AWG main, 6 AWG branches)
- Safety logic: JK BMS â†’ contactor, coil fused; emergency open behaviour
- Exports present and named correctly (SVG, PNG, A3/A2 PDFs)

## Checklist
- [ ] DC schematic **R1.4c** accepted  
- [ ] AC schematic **R0.3** accepted  
- [ ] BOM aligns with specs and AU/NZ sourcing  
- [ ] Installation steps clear for commissioning  
- [ ] Safety notes cover contactor/BMS logic and PV handling  
- [ ] Folder structure (`diagrams/`, `docs/`, `bom/`) correct  

---

### Notes
- No changes to functional design versus previously agreed **R1.4c**; this PR is to formalise review and sign-off.
- If any edits are requested (labels, routing, values), please comment inline and we will update the source `.drawio` files and regenerate exports accordingly.

