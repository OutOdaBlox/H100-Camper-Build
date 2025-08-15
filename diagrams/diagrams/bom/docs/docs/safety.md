# Safety (R1.4c)

General
- Follow device manuals and local electrical regulations.
- De-energize before service; confirm with meter; use PPE.

Protection
- Battery positives individually fused (MEGA 100 A).
- Main contactor (TE EV200) used as system disconnect under JK BMS control.
- Inverter protected by Class-T 200 A near + bus.
- Distribution, MPPT, DC-DC protected by appropriately sized fuses.

BMS/Contactor Logic
- JK BMS low/high-voltage or temperature events open the main contactor.
- Coil feed must be fused and on protected supply.
- Optional: manual emergency stop in coil circuit.

Grounding/Bonding
- Follow Victron guidance for DC negative/AC earth bonding.
- RCD/MCB on AC distribution; shore input protected per code.

PV
- PV isolator DC-rated; treat connectors live in sunlight.
- Use UV-rated 10 AWG (6 mm2) PV cable and MC4 connectors.
