# Full Camper Electrical Build â€“ 1996 Toyota Hiace KZH100

## Key Clarification
- **Valence U27-12XP batteries include an internal BMS for cell protection and balancing**, but *do not provide high-current load disconnection*.  
- An **external JK 4S LiFePOâ‚„ Smart BMS (150â€“200 A)** must be used to control a main contactor in the positive line for safety and low-voltage disconnect.

## Overview
Generate updated wiring diagrams, BOMs, and install guides **from scratch**.

## Components & Specs
1. Batteries: 2 Ã— Valence U27-12XP (parallel, internal BMS)
2. External BMS: JK 4S LiFePOâ‚„ Smart BMS, 150â€“200 A with temp sensors
3. Main contactor: High-current DC contactor (EV200)
4. SmartShunt 500 A; bus bars, solar system, DC-DC, inverter
5. Outputs: 1 Ã— inverter AC outlet, 2 Ã— 12V/USB (A + C), water pump (10 A), lights (5 A)
6. Victron Orion-Tr Smart 12/12-30A **isolated**
7. Diagram export: draw.io CLI â†’ `.drawio`, `.svg`, `.png`
8. Retail: best-value AU/NZ retailers across wide mix

## Deliverables
- `/diagrams/dc_schematic.*` with JK BMS, main contactor, auto isolation logic
- `/diagrams/ac_schematic.*` with dashed shore power inlet
- `/bom/bom.csv` with prices/links
- `/docs/installation.md` step-by-step
- `/docs/safety.md` safety logic & testing

## Execution Logic
- Maintain A3 visibility, fuse-gauge labeling, and wiring clarity
- Include cable runs: solar to battery ~3m, alternator to battery 1.5m, water pump 3m, others ~1m
- Use best-value AU/NZ sources (Jaycar, RS, TradeMe, AME, etc.)
- All wire gauge specs in mmÂ² and AWG


