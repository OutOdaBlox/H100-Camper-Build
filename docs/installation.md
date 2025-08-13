# Installation Guide  
1996 Toyota Hiace KZH100 – Camper Electrical System

Refer to the DC and AC schematics in `/diagrams/*.`  

---

## 1  Planning & Parts Check
1. Print the schematics (A3) and keep on-hand.  
2. Verify all components against `/bom/bom.csv`:  
   • Batteries: **2 × Valence U27-12XP (parallel, internal BMS)**  
   • **External JK 4S LiFePO₄ Smart BMS 150–200 A** – *contactor control only; no cell taps into Valence packs*  
   • Victron SmartShunt 500 A, SmartSolar MPPT 100/30, Orion-Tr Smart 12/12-30A isolated, Phoenix 12/1000 inverter.  
3. Confirm fuses, cable, lugs, heat-shrink, and tools are on site.

### Wire & Fuse Inventory

| Circuit | Length | Size mm² (AWG) | Fuse / Breaker |
|---------|--------|----------------|----------------|
| Batteries ↔ Busbar | 0.3 m | 35 mm² (2 AWG) | Class-T 200 A |
| Busbar ↔ Inverter | 1 m | 35 mm² (2 AWG) | MEGA/Class-T 150 A (inverter branch) |
| Busbar ↔ Orion | 1.5 m | 6 mm² (10 AWG) | MIDI 40 A |
| Busbar ↔ MPPT | 3 m | 10 mm² (8 AWG) | MIDI 40 A |
| Busbar ↔ Loads fuse block | 1 m | 6 mm² (10 AWG) | per-load ATC |
| Solar panels ↔ MPPT | 3 m | 4 mm² (12 AWG, PV rated) | PV inline 15 A (each panel) |
| JK BMS ↔ Contactor coil | 0.3 m | 1 mm² (18 AWG) | n/a (logic) |

---

## 2  Safety Precautions
• Disconnect vehicle negative before work.  
• PPE: insulated gloves, eye protection.  
• Torque all studs to spec (Phoenix 12/1000: 9 Nm, SmartShunt: 10 Nm).  
• No metal jewellery; ventilate battery bay; Class D extinguisher ready.  
• AC wiring must be installed / certified by a licensed electrician – **AS/NZS 3001.2** applies.

---

## 3  Mounting Locations (Hiace)
| Component | Suggested Position | Notes |
|-----------|-------------------|-------|
| Battery bank | Under rear bench | Strapped, vented |
| JK BMS & contactor | Beside batteries | ≤150 mm positive link |
| Pos/Neg busbars & fuse block | Above battery box | Clear covers |
| SmartShunt | Battery − post (load side) | Arrow → loads |
| MPPT 100/30 | Rear pillar cavity | ≤1 m to bus |
| Orion-Tr | Under driver seat | Close to starter batt |
| Inverter | Under bench, ventilated | 100 mm airflow |
| AC RCD + MCB + outlet | Cabinet face | Splash protected |
| Solar entry gland | Roof rear | Drip-loop inside |

---

## 4  Cable Routing & Preparation
1. Run positive/negative pairs together; protect in split loom.  
2. Separate DC and AC by ≥50 mm.  
3. Support every 300 mm with P-clips; grommet through metal.  
4. Crimp with hex/indent tool, heat-shrink, label both ends.

---

## 5  Installation Steps – DC
1. Negative path: **battery – → SmartShunt 500 A → negative busbar**.  
2. Positive path: **battery + → Class-T 200 A (≤150 mm) → main contactor 200 A → positive busbar**.  
3. Wire JK BMS power (2 A blade fuse) and coil driver to contactor; fit temp probes to battery case.  
4. Solar: 2 × 200 W parallel → MC4 Y → 15 A inline MC4 fuses → 6 mm² red/black ~3 m → MPPT 100/30 → 40 A MIDI → bus.  
5. Alternator/DC-DC: starter batt → 40 A fuse → 6 mm² ~1.5 m → Orion-Tr 12/12-30A (isolated) → 40 A fuse → bus; remote on/off via ignition D+.  
6. Inverter: bus → 35 mm² ~1 m → 150 A MEGA/Class-T → Phoenix 12/1000; bond chassis with 16 mm² green/yellow.  
7. Distribution: bus → 60 A MIDI → Blue Sea 12-cct; fit blade fuses (pump 10 A, lights 5 A, USB 15 A ea).  
8. *Optional* pre-charge: place **1 kΩ 5–10 W resistor** across contactor/inverter + for ~5 s before closing.

---

## 6  Installation Steps – AC
1. Phoenix AC output → 2-pole RCD 30 mA → 10 A MCB → single AU/NZ outlet (label “INVERTER SUPPLY ONLY 230 V”).  
2. Shore inlet & 2-pole transfer switch remain dashed/unwired for future fit-out.  
3. Earth bar bonded to chassis with 16 mm² cable.

---

## 7  Device Configuration
### 7.1  Victron SmartSolar MPPT 100/30
- Battery preset LiFePO₄: Absorption **14.2 V**, Float **13.5 V**, Equalise OFF, temp comp OFF.

### 7.2  Victron Orion-Tr Smart 12/12-30A (Isolated)
- Abs 14.2 V / Float 13.5 V.  
- Remote on/off: IGN D+.  
- Input UV: **start 12.8 V / stop 12.4 V**.

### 7.3  Victron Phoenix 12/1000
- DIPs: Search OFF (continuous).  
- Connect VE.Direct for monitoring.

### 7.4  Victron SmartShunt 500 A
- Capacity **276 Ah** (2 × 138 Ah).  
- Orient **BATT- → LOAD-**.  
- Charged voltage 13.5 V for >4 min; tail current 2 %.  
- Perform SOC sync at full charge.

### 7.5  JK 4S LiFePO₄ Smart BMS
- *No cell taps*: pack ± only.  
- Low-V cut 11.0 V; High-V cut 14.4 V; delay 5 s.  
- Coil drive → main contactor; failsafe opens on power loss.

---

## 8  Commissioning & Testing
### 8.1  Pre-flight Checklist
- [ ] All crimps pull-tested, heat-shrunk  
- [ ] Fuses per inventory table installed  
- [ ] Torque lugs (35 mm² @ 20 Nm)  
- [ ] Batteries secured & vented  
- [ ] RCD trip-tested  
- [ ] Schematics printed onboard  

### 8.2  First Power-Up
1. Cover solar, inverter OFF.  
2. Close negative, then manually close contactor via JK app.  
3. Verify SmartShunt voltage ~13 V.  
4. Start engine, enable Orion; confirm 30 A charge.  
5. Uncover solar; check MPPT current.  
6. Switch inverter ON; apply 100 W load; watch voltage & temp.  
7. Sync SmartShunt at 100 % SOC.

---

## 9  Maintenance & Compliance
- Retorque lugs after first 100 km then annually.  
- Inspect cables, replace UV-damaged ties.  
- Firmware updates via VictronConnect.  
- Annual battery capacity test (cycle 20 %→100 %).  
- Any AC modifications must meet **AS/NZS 3001.2** and be signed off by a licensed electrician.

*Installation complete – enjoy safe off-grid power!*  
