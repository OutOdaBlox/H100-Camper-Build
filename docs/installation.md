# H100 Camper Electrical – Installation (R1.4c)

Summary
- Batteries: Valence U27-12 (x2)
- BMS: JK BMS 8S 2A (controls TE EV200 contactor)
- MPPT: Victron SmartSolar 100/30
- DC-DC: Victron Orion-Tr Smart 12/12-30A
- Inverter/Charger: Victron MultiPlus 12/2000
- Solar: 2 × 200 W in series, PV isolator, SmartShunt 500A
- 12V Distribution: Blue Sea 5029, bus bars Blue Sea 2104/2105

Wiring Notes
- Main runs: 2/0 AWG for battery/contactor/inverter.
- MPPT/DC-DC: 6 AWG typical (adjust per length and current).
- Battery fuses: MEGA 100 A each battery positive.
- Inverter fuse: Class-T 200 A near + bus.
- Distribution/MPPT/DC-DC fuses: 60 A typical (adjust per device spec).

PV (2 × 200 W, series)
1. Wire panels in series on the roof (Panel 1 + to Panel 2 -).
2. Bring pair into roof gland → PV isolator → MPPT PV IN.
3. Confirm MPPT 100/30 voltage/current limits are respected.

SmartShunt
- Battery negatives to battery side of shunt; system negatives to load side.
- Tighten per manufacturer torque specs.

Contactor & JK BMS
1. Place TE EV200 in battery positive path before + bus.
2. Power coil from protected fused feed (1–3 A fuse typical).
3. JK BMS output drives coil via control relay (per JK wiring).
4. Configure LVD/HVD/Temp in JK app.

Commissioning
1. Verify polarity and torque on all terminations.
2. Close PV isolator and confirm MPPT sees array Voc.
3. Enable JK BMS, close contactor (precharge via controller if applicable).
4. Power MultiPlus and verify AC output with no loads.
5. Check charge sources (MPPT, DC-DC) current and voltage.
6. Record baseline values in SmartShunt.
