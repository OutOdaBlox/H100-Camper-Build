# Electrical Safety & Testing Guide  
1996 Toyota Hiace KZH100 Camper – 12 V LiFePO₄ System (AU/NZ)

---

## General Safety
- PPE: 1000 V insulated gloves, safety glasses, cotton overalls, non-conductive footwear.  
- Remove metal jewellery; keep sparks/flammables away from battery bay.  
- Work de-energised: disconnect **negative, then positive**; verify zero volts.  
- Torque all lugs to manufacturer spec (e.g. Phoenix 12/1000: 9 Nm; SmartShunt: 10 Nm).  
- Class D extinguisher within reach; ventilate while charging.

---

## Cable Sizing & Voltage-Drop Targets  
*(< 3 % on high-current branches @ 12 V)*  

| Branch | Current (A) | Length (1-way) | Size mm² (AWG) | Drop | Status |
|--------|-------------|---------------|----------------|------|--------|
| Batt ↔ Busbars | ≤200 | 0.5 m | 50 (1/0) | 1 % | ✓ |
| Busbar ↔ Inverter | 100 | 1 m | 35 (2) | 2 % | ✓ |
| Solar ↔ MPPT | 20 | 3 m | 6 (10) | 1.2 % | ✓ |
| MPPT ↔ Busbars | 30 | 1.5 m | 10 (8) | 1.8 % | ✓ |
| Orion ↔ Starter batt | 30 | 1.5 m | 6 (10) | 1.8 % | ✓ |

---

## Fusing Strategy & Placement
- **Class-T 200 A** main fuse ≤150 mm from battery +.  
- **150 A MEGA/Class-T** on inverter branch at busbar.  
- **40 A MIDI** on MPPT positive, **40 A MIDI** on Orion input & output positives.  
- **15 A MC4** inline fuse per 200 W panel.  
- Blade fuses at Blue Sea fuse block: pump 10 A, lights 5 A, USB outlets 15 A each.  
- Store spare fuses & puller in service bay.

---

## Bus Bars & Enclosures
- Blue Sea 600 A tinned-copper bars in IP54 polycarbonate box with clear cover.  
- Maintain ≥50 mm separation between + and –; label polarity (red/black heat-shrink).  
- No exposed studs; torque check quarterly.

---

## JK BMS Contactor Control Logic & Limitations
- Valence U27-12XP provide **internal cell BMS**; **no external cell taps** used.  
- JK 4S Smart BMS monitors pack voltage/temp only → drives 12 V coil contactor.  
- Pack LVD 11.0 V, HVD 14.4 V, delay 5 s.  
- **Fail-safe:** loss of JK power opens contactor.  
- Pre-charge: fit **1 kΩ 5–10 W resistor** across contactor/inverter + for ~5 s before closure.

---

## Alternator / DC-DC Best Practices
- Orion-Tr Smart 12/12-30A **isolated**; input from starter via 40 A fuse.  
- Remote on/off via ignition (D+) to prevent draining starter battery.  
- 35 mm² copper braid from service negative bus → chassis ≤300 mm.

---

## Solar PV Safety
- Open-circuit array < 23 V (parallel 2 × 200 W) – still isolate before service.  
- Use genuine MC4; crimp with PV die; polarity-check with multimeter.  
- Inline 15 A MC4 fuses within 300 mm of roof junction.

---

## AC Specifics
- Phoenix 12/1000 → **2-pole RCD 30 mA** → **2-pole 10 A MCB** → single NZ GPO.  
- Inverter neutral floats; earth bonded to chassis with 16 mm² G/Y cable.  
- Shore inlet & 2-pole transfer switch shown **dashed** (future fit).  
- Must comply with **AS/NZS 3001.2**; licensed electrician sign-off required.

---

## Commissioning Tests
- Continuity: chassis bonds < 0.1 Ω.  
- Insulation: 500 V megger between DC + and chassis ≥1 MΩ.  
- Fuse audit vs table above; covers fitted.  
- RCD trip (<30 mA, <40 ms) & polarity check.  
- Configure MPPT (14.2 V/13.5 V) & Orion (14.2 V/13.5 V, UV 12.4 V).  
- SmartShunt: set 276 Ah cap, perform 100 % sync.  
- Simulate JK BMS LVD to confirm contactor opens.  
- Inverter load test: 800–1000 W for 10 min – batt >11.5 V, temp <70 °C.  
- Thermal scan: no hotspot >15 °C above ambient.

---

## Periodic Maintenance (Quarterly)
- Re-torque battery & busbar lugs; inspect cables for chafe/UV.  
- Clean MC4 & battery posts; apply dielectric grease.  
- Firmware updates (VictronConnect).  
- Cycle batteries 20 %→100 % annually to verify capacity.  
- Record tests in service log; keep printed copy of this guide in glovebox.

---
