# CarbonPrints – 10-Printer Farm Operations & Maintenance Manual

## 1. Operating Environment & Climate Challenges (Chennai Context)

Operating a 10-printer additive manufacturing setup in Chennai requires specific climate management due to high relative humidity (65%–85%) and elevated ambient temperatures (30°C–38°C).

```
┌─────────────────────────────────────────────────────────────┐
│                 CHENNAI CLIMATE MANAGEMENT                 │
├──────────────────────────────┬──────────────────────────────┤
│ Humidity (65% - 85%)         │ Heat & Air Drafts            │
│ • Hydrophobic Dryboxes       │ • Enclosures for ABS         │
│ • Active Silica Desiccant    │ • Controlled airflow         │
│ • Seal spools immediately    │ • AC / Fan draft protection  │
└──────────────────────────────┴──────────────────────────────┘
```

---

## 2. Material Processing Protocols (PLA, ABS, TPU)

### 2.1 PLA (Polylactic Acid) – Visual Models & Display Prototypes
* **Cost Basis:** ₹4.00 / gram (wholesale bulk). Selling Price: ₹7.00 – ₹8.00 / gram.
* **Extruder Temp:** 200°C – 210°C | **Bed Temp:** 55°C – 60°C.
* **Print Surface:** Textured PEI Sheet. Clean with 99% Isopropyl Alcohol (IPA) every 3 prints.
* **Cooling Fan:** 100% after layer 2.
* **Chennai Climate Rule:** PLA can absorb ambient moisture within 2 weeks if left open in Chennai, leading to brittle filament that snaps inside the Bowden tube. Always feed directly from dryboxes or reseal with silica gel bags when not in use.

### 2.2 ABS (Acrylonitrile Butadiene Styrene) – Engineering & Functional Parts
* **Cost Basis:** ₹4.00 / gram. Selling Price: ₹9.00 – ₹11.00 / gram.
* **Extruder Temp:** 235°C – 245°C | **Bed Temp:** 95°C – 105°C.
* **Print Surface:** Smooth PEI with thin layer of PVA glue stick or Kapton tape to prevent thermal warping.
* **Cooling Fan:** 0% – 15% (rapid cooling causes severe layer separation / splitting).
* **Enclosure Requirement:** ABS **MUST** be printed in a draft-free enclosure (tent or acrylic chamber). An ambient enclosure temperature of 40°C–50°C prevents corner lifting.
* **Safety & Fume Ventilation:** ABS emits styrene fumes and ultrafine particles. Never run ABS printers in an unventilated bedroom or closed room without an exhaust fan or active carbon HEPA air purifier. Interns must be trained on this safety rule.

### 2.3 TPU (Thermoplastic Polyurethane - 95A) – Flexible & Shockproof Parts
* **Cost Basis:** ₹4.50 / gram. Selling Price: ₹12.00 – ₹14.00 / gram.
* **Extruder Temp:** 215°C – 225°C | **Bed Temp:** 45°C – 50°C.
* **Extruder Setup:** Requires direct-drive extruder or very short constrained filament path. Loosen the extruder arm idler tension so the gears do not crush the flexible rubber.
* **Speed & Retraction:**
  - Print speed: Slow down to **20 – 30 mm/s** (fast printing causes TPU to buckle around the feeder gear).
  - Retraction: Disable or minimize to <1.5mm at 20mm/s.
* **Moisture Sensitivity:** TPU is highly hygroscopic. Wet TPU pops and sizzles at the nozzle, leaving rough, stringy, bubbly surfaces. Dry TPU at 55°C for 4 hours in a dedicated food dehydrator or filament dryer before major prints.

---

## 3. Farm Slicing Standards (Cura / PrusaSlicer Profiles)

To maintain consistent quality across 10 machines, interns must adhere to these 3 standardized profiles:

| Parameter | Draft Profile (Speed) | Standard Profile (Default) | High-Precision Profile |
| :--- | :--- | :--- | :--- |
| **Layer Height** | 0.28 mm | 0.20 mm | 0.12 mm |
| **Initial Layer Height** | 0.28 mm | 0.20 mm | 0.20 mm |
| **Wall Line Count** | 2 lines (0.8 mm) | 3 lines (1.2 mm) | 4 lines (1.6 mm) |
| **Top / Bottom Layers** | 3 layers | 4 layers | 6 layers |
| **Default Infill** | 15% Grid | 20% Gyroid (isotropic strength) | 35%–50% Gyroid / Cubic |
| **Print Speed** | 60–75 mm/s | 45–55 mm/s | 30–40 mm/s |
| **Support Type** | Tree Supports (55° threshold) | Tree Supports (50° threshold) | Normal / Dense Interface |
| **Build Plate Adhesion** | Skirt | Brim (5mm for ABS) | Brim / Raft |

---

## 4. Preventive Maintenance Checklist

Regular maintenance on 10 printers prevents costly mid-print failures and customer deadline delays:

### Daily Shift Checklist (Each Morning by Tech Intern)
- [ ] Inspect PEI beds for residue; clean with 99% IPA using lint-free microfiber cloth.
- [ ] Check nozzle for filament buildup; brass-wire brush nozzle when heated to 180°C.
- [ ] Verify hotend fan and part cooling fans spin freely without bearing noise.
- [ ] Inspect Bowden tube couplers for play (slipping tube causes chronic clogging).

### Weekly Maintenance Checklist (Every Saturday Afternoon)
- [ ] **Bed Leveling Verification:** Run a 5-point bed tramming check; ensure Z-offset is within ±0.05mm.
- [ ] **Belt Tension Check:** Pluck X and Y belts; they should produce a low acoustic vibration (taut, not guitar-string tight, never loose).
- [ ] **Lead Screw Lubrication:** Wipe Z-axis lead screws clean of dust and reapply white lithium grease or synthetic PTFE lubricant.
- [ ] **V-Slot Roller Wheel Inspection:** Check POM wheels for flat spots or black rubber dust; adjust eccentric nuts if loose.

### Monthly / 500-Hour Overhaul (Founder Oversight)
- [ ] **Nozzle Replacement:** Swap worn 0.4mm brass nozzles (abrasive pigments in ABS/matte filaments erode nozzle orifices to >0.5mm, causing over-extrusion and stringing).
- [ ] **Frame Rigidity Check:** Tighten all M4/M5 frame structural bolts.
- [ ] **Thermal Runaway Protection Test:** Verify firmware triggers error shutdown if thermistor is disconnected or heater cartridge decoupled.

---

## 5. Quality Control (QC) & Dispatch Gate

Before any part leaves the CarbonPrints workshop:
1. **Dimensional Inspection:** Intern uses digital vernier calipers to check critical mounting holes, bore diameters, and outer envelope against the client's CAD drawing (tolerance standard: ±0.2mm).
2. **Support Cleanup:** Carefully remove all tree supports with flush cutters; deburr contact scars with a hobby knife or light 400-grit sandpaper.
3. **Weight Confirmation:** Place the part on a digital precision scale (0.1g resolution) and record the actual final weight in the Operations Sheet.
4. **Protective Packaging:**
   - Wrap each part in bubble wrap.
   - For ABS parts with delicate clips, pack in rigid corrugated boxes with crumpled kraft paper filler.
   - Enclose the **Printed Tax Invoice / Delivery Slip** inside the box.
   - Seal with fragile tape and attach courier dispatch barcode.
