# Campus Workshop & Technical Seminar Deck: "Design for Additive Manufacturing"

**DOCUMENT CLASSIFICATION:** Educational Collateral / Event Presentation Script
**SUITABLE EVENT:** 45-Minute Departmental Seminar, Tech-Fest Workshop, or Robotics Society Masterclass
**DELIVERED BY:** CarbonPrints Campus Ambassador & Student Fellow
**VERSION:** 2.0 · September 2026 · Upgraded with Formula Bharat/Robocon Case Studies & AICTE IDEA Lab Positioning

---

## Workshop Overview & Organizer Setup

* **Title:** *Design for Additive Manufacturing (DFAM): From CAD to Functional Prototype*
* **Target Audience:** Mechanical, Mechatronics, Aerospace, Automobile, Robotics, and Product Design students (2nd–4th year).
* **Duration:** 45 Minutes Presentation + 15 Minutes Interactive Slicing Demo & Q&A.
* **Maximum Attendance:** 50 students per session for interactive quality. Larger groups okay with 2 audience microphones.
* **Organizer Checklist:**
  * Projector with HDMI input (have a USB-C adapter for MacBook users).
  * Laptop with **PrusaSlicer** or **UltiMaker Cura** pre-installed + **3 sample STL files** pre-loaded.
  * Display Table: planetary gearbox showcase print, material swatch ring (PLA/PETG/ABS/TPU/CF-PETG), robot arm bracket.
  * A3 event posters displayed outside the seminar hall with registration QR code.
  * Google Form link for post-event feedback + CarbonPrints quote request (same form).
  * 10 printed one-page reference sheets: "Material Selection Quick Guide" (from Doc_04, Section 1).

---

## PRE-WORKSHOP PREP: Getting Permission & Promotion

Before the workshop:
1. Submit the HOD Permission Letter (Doc_06, Template 3.1) at least **5 working days** before the event.
2. Once approved, post in the departmental WhatsApp group using Template 1.1 from Doc_06.
3. Create a Tally.so RSVP form to track attendee count for PoW verification (min 20 students required for 300 Ambassador Points).
4. Bring physical showcase prints — the moment students hold a planetary gearbox or feel TPU flex, the rest of the workshop sells itself.

---

## Module 1: The Prototyping Revolution & Modern Additive Manufacturing (Slides 1–6)

### Slide 1: Title & Presenter Introduction
* **Visual:** Dark-themed slide. CarbonPrints logo. Bold: *"Design for Additive Manufacturing (DFAM): Build Functional Engineering Prototypes in 24 Hours"*
* **Speaker Script:**
  > *"Good afternoon. I'm [Name], [Year/Dept] here at [College Name] and Campus Fellow for CarbonPrints Private Limited — an industrial 3D printing facility in Chennai. Today we're not doing theory. We're going to cover exactly why prints fail, how to fix them, which materials to use for which applications, and how to get real precision-manufactured parts for your capstone project or club build in 24 to 48 hours. By the end, you'll know more about production-grade 3D printing than most engineering graduates."*

### Slide 2: The Hardware Prototyping Problem in Indian Engineering
* **Visual:** Timeline: College lab queue (10 days) vs. local 3D printing (24 hours).
* **Key Point:** The average Anna University-affiliated mechanical engineering capstone team loses 3–4 weeks per semester waiting for lab printer access. In that time, 3D printing delivers 3–4 complete design iterations.
* **Stat:** Indian engineering colleges collectively have fewer than 1 FDM printer per 200 engineering students. Industrial services like CarbonPrints exist to bridge this gap.

### Slide 3: The Manufacturing Spectrum (Subtractive vs. Formative vs. Additive)
* **Visual:** Three-column diagram. Left: CNC machining (cutting away, high tooling cost). Center: Injection molding (expensive steel mold, min 50k parts). Right: FDM (layer-by-layer, zero tooling, geometric complexity is free).
* **Key Point:** Additive is the only process where complexity is essentially free. A hollow gyroid lattice internal structure costs less to print than a solid block.

### Slide 4: Where Industrial FDM Dominates — vs. SLA and SLS
* **Visual:** Comparison table of FDM (large-format, engineering polymers), SLA (resin, high detail), SLS (nylon powder, no supports). Price bands for each.
* **Key Point for Students:** SLA is great for tiny intricate dental/jewelry models. SLS is great for production nylon parts. Industrial FDM is the undisputed king for **functional, large-scale, impact-resistant engineering parts** — which is what 90% of student projects need.

### Slide 5: The Real Economics of Student Engineering Projects
* **Visual:** Pie chart: Typical ₹15,000 capstone project budget. Where it gets wasted (machine shop attempts, failed lab prints, laser-cutting mistakes) vs. where 3D printing delivers ROI (rapid iteration, functional prototyping before committing to machining).
* **Key Point:** On average, 3D printing 3 prototype iterations before final machining saves ₹4,000–₹8,000 on a typical student project budget.

### Slide 6: Case Study — Formula Bharat / SAE Baja Vehicle Bracket Optimization
* **Visual:** Before: Machined aluminum suspension telemetry bracket (500g, 3-week lead time, ₹6,000 machining cost). After: CF-PETG 3D printed bracket (290g, 18 hours, ₹800).
* **Key Point:** 42% weight reduction. Zero machining wait-time. Teams like Astral Racing (Sathyabama), Camber Racing (SRM), and Shaurya Racing (VIT Chennai) use additive manufacturing for their non-safety-critical vehicle components in exactly this way.

---

## Module 2: Design for Additive Manufacturing (DFAM) Fundamentals (Slides 7–14)

### Slide 7: The #1 Mistake Engineering Students Make — Anisotropy
* **Visual:** Microscopic cross-section of FDM layers. Arrow showing XY tensile strength (100%) vs. Z-axis tensile strength (30%).
* **Speaker Script:**
  > *"Here is the single most common reason student 3D prints snap: people assume FDM parts are isotropic like injection-molded plastic. They are not. Tensile strength along the X-Y plane is 3 times higher than along the Z-axis. Your part MUST be oriented on the print bed so that the primary load path runs parallel to the layer lines — never perpendicular. If you get this one thing right, your prints will last. If you get this wrong, they will snap under any real load."*

### Slide 8: The 45-Degree Overhang Rule & Support-Free Geometry
* **Visual:** Diagram of 45° threshold. Parts above 45° that droop without support, parts chamfered at 45° that print support-free.
* **Design Tip:** Chamfer all internal holes and downward-facing overhangs at 45° to eliminate support structures entirely. Zero supports = cleaner surface, less post-processing, lower print cost.

### Slide 9: Bridge Geometry & Active Cooling
* **Visual:** 50mm horizontal bridge printed cleanly with high-speed cooling fan.
* **Key Point:** FDM printers can bridge horizontal spans up to 60–80mm without supports if proper bridging speed and part-cooling fan settings are applied. No need to add supports for every small horizontal span.

### Slide 10: Infill Topologies — Why Gyroid Beats Grid
* **Visual:** Side-by-side mechanical compression test data. Grid infill (nozzle collision points, stress concentrations), Honeycomb (strong in one axis), Gyroid (near-isotropic strength, all 3 axes).
* **Hard Rule:** **Never use Grid infill for functional parts.** Grid infill crosses over itself and creates nozzle collision artifacts. Always use **Gyroid infill** for any load-bearing part — near-isotropic shear strength at 20% fill density.

### Slide 11: Wall Perimeters — The True Source of Part Strength
* **Visual:** FEA stress distribution diagram. Thin walls (2 perimeters) vs. thick walls (5 perimeters). Shows stress concentrated in outer shell, not infill.
* **Pro Tip:** Want a dramatically stronger part? **Do NOT increase infill from 20% to 100%.** Instead, increase perimeter wall count from 2 to 5. Approximately 80% of bending stiffness comes from the outer perimeter shells. Thick walls + Gyroid infill at 20% outperforms thin walls + 60% Grid infill.

### Slide 12: Tolerances for Bearings, Press-Fits & Heat-Set Inserts
* **Visual:** Exploded CAD diagram of a robot joint with 608-2RS bearing, M3 brass heat-set insert, and M4 socket head bolt.
* **Key Numbers:**
  * Internal bore for **608-2RS bearing (22mm OD):** Design to **22.3mm** (add +0.3mm clearance).
  * M3 brass heat-set insert hole: **4.0mm** (tight fit, heat-sets flush on insertion).
  * Clearance fit for assembly: **+0.2mm** on mating surfaces.
  * Always use **heat-set brass threaded inserts** (M2–M6) instead of tapping plastic directly — 10x stronger thread retention.

### Slide 13: Eliminating Non-Manifold Geometry (The Most Common CAD Error)
* **Visual:** SolidWorks/Fusion 360 screenshot showing open surface boundaries (red edges), zero-thickness surfaces, and inverted normals.
* **Fix Workflow:** In Fusion 360: *Mesh workspace → Repair → Fix Non-Manifold Edges.* In SolidWorks: *Export → Check geometry before STL export.* In Meshmixer: *Analysis → Inspector → Fix All.*
* **Rule:** Always export as **Binary STL** (not ASCII) with high resolution (angular deflection < 0.5°). Or export as **STEP** format for smooth curved surfaces with no tessellation artifacts.

### Slide 14: Designing for Disassembly & Assembly — The Student's Blind Spot
* **Visual:** Modular printed assembly with captive nuts, snap-fit joints, and dovetail connectors.
* **Key Point:** Students often design entire assemblies as monolithic single prints. Always split complex assemblies into printable sub-components with designed-in assembly features (snap-fits, magnets, captive hardware). Leads to stronger final assemblies and cleaner surface finishes on visible faces.

---

## Module 3: Advanced Engineering Materials (Slides 15–19)

### Slide 15: Beyond White PLA — Engineering Polymer Families
* **Visual:** Material swatch ring display — show physical swatches to the audience.
* **Speaker Script:**
  > *"Pick up one of the swatch rings being passed around. Feel the difference between PLA, PETG, TPU, and CF-PETG. These are not the same material printed in different colors. Each has fundamentally different mechanical properties. The right material choice makes or breaks your prototype."*

### Slide 16: PETG (The Engineering Workhorse)
* **Properties:** High chemical resistance, semi-flexible toughness, 75°C heat resistance, fully waterproof, food-safe (uncoated), UV-stable.
* **Ideal Applications:** ⭐ Drone arms, snap-fit enclosures, outdoor sensor housings, Formula Bharat telemetry brackets, waterproof robot chassis components.
* **When NOT to use it:** Parts that need acetone-smoothed finish (use ABS) or extreme heat (use ASA/ABS).

### Slide 17: ABS & ASA (Heat Resistance & Durability)
* **ABS Properties:** Heat resistance to 95°C, impact-ductile, can be acetone-vapor smoothed to airtight, injection-molded appearance.
* **ASA Properties:** Same as ABS + UV-stable for outdoor use. Superior long-term weathering.
* **Ideal Applications:** ⭐ SAE Baja/Formula engine bay brackets, exhaust-adjacent sensor housings, sandable cosmetic prototypes, agri-drone outdoor components.

### Slide 18: TPU 95A Elastomer (The Indestructible Flexible)
* **Properties:** Shore 95A hardness (rubber-like), complete impact absorption, oil/grease resistant, chemical resistant, 80°C heat resistance.
* **Ideal Applications:** ⭐ Robot all-terrain tires, Robocon bumper end-caps, motor vibration dampers, wire grommets, airtight gaskets, drone landing gear tips.
* **Print Tip:** TPU requires slow print speed (25–35 mm/s) and Bowden extruder avoidance — use direct-drive extruder printers (CarbonPrints farm is direct-drive equipped).

### Slide 19: CF-PETG & CF-Nylon (The Structural Champions)
* **Properties:** Chopped micro-carbon fibers suspended in PETG or Nylon matrix. Extreme rigidity, low weight, high dimensional stability, zero warping, stealth matte finish.
* **Ideal Applications:** ⭐ High-torque robotic gripper arms, UAV motor mounts, Formula Student steering components, suspension jig fixtures, drone chassis structural members.
* **Trade-off:** Abrasive to brass nozzles — requires hardened steel nozzles (CarbonPrints farm is CF-ready).

---

## Module 4: Live Slicing Demo, Economics & Getting Started (Slides 20–25)

### Slide 20: Live Slicing Demonstration (Interactive Laptop Display)
* **Action:** Switch screen to PrusaSlicer / UltiMaker Cura.
* **Live Demo Script:**
  > *"Okay — I'm importing the robot bracket STL that [volunteer from audience] just sent me during the last break. Watch what happens when I import it without checking. See this? The orientation is wrong — the wide flat face is vertical, which means the layer lines will run parallel to the bending axis. That's a guaranteed snap point under load. First fix: rotate it 90 degrees so the flat face is on the bed. Second: switch infill from Grid to Gyroid at 20%. Third: change perimeter walls from 2 to 4. Now watch what happens to the print time and cost."*
* **Show:** Print time before optimization (4h 30m), after optimization (3h 15m), and cost reduction (₹340 → ₹280).

### Slide 21: The Transparent Cost Formula — No Mystery Pricing
* **Visual:** Sliced part data on screen.
  $$\text{Client Price} = (\text{Weight in grams} \times \text{Material Base Rate/gram}) + \text{Machine Setup Fee}$$
* **Example:** 42g PETG × ₹4/g + ₹100 setup = **₹268 base price** → **₹241 with student code (10% off)**.
* **Key Message:** No hidden charges. No arbitrary quotes. You pay exactly for the material your design uses plus the machine time. That's why we use transparent slicing data.

### Slide 22: Inside the CarbonPrints Farm
* **Visual:** Photo of the 10-printer FDM farm — show active calibrated machines, climate-controlled filament storage, QC caliper station.
* **Key Point:** 10 machines operating simultaneously = high-capacity parallel printing. A 5-part robotic arm assembly is distributed across 5 machines and completed in 12 hours simultaneously, versus 4 days on a single lab printer.

### Slide 23: Quality Control, Dispatch & the Reprint Guarantee
* **Visual:** Caliper inspection of printed part (±0.2mm tolerance check) + 5-layer bubble-wrap packaging + Porter delivery screenshot.
* **Three Pillars of CarbonPrints QC:**
  * ✅ Dimensional verification with digital caliper before dispatch
  * ✅ Visual inspection for delamination, stringing, or warping
  * ✅ 100% Free Reprint Guarantee for any production-attributed defect

### Slide 24: Club Manufacturing Partnerships & AICTE IDEA Lab Opportunities
* **Visual:** Logos of Formula Bharat, SAE India, Robocon, and AICTE.
* **The Club Partnership Offer:**
  * Formula Student/Baja/Robocon teams: 15% bulk seasonal discount + priority queue + DFM consultation + optional CarbonPrints vehicle decal.
  * AICTE IDEA Lab partner colleges: 20% lab project discount + co-branded workshop sessions + industry mentor availability.
* **Script:** *"If your team is registered for Formula Bharat or Robocon this season, talk to me after the session. I can connect your technical director directly with our Founder for a formal manufacturing partnership conversation."*

### Slide 25: Your Exclusive Campus Offer + Q&A + Part Inspection
* **Visual:** Large slide with the Ambassador's custom QR code and referral code `{{UNIQUE_REFERRAL_CODE}}`.
* **The Offer:** **10% Instant Student Discount** on first print order + Free CAD DFM Review from the engineering team.
* **Action:** Invite students to the front display table to physically handle, bend, test, and examine all showcase prints and material swatches.
* **Script:** *"Come up, pick up the planetary gear. Try to break the TPU tire. Feel the CF-PETG bracket. If you have an STL file on your phone right now, share it with me and we'll have a quote in 15 minutes. Scan my QR code for 10% off your first order. Thank you."*

---

## Post-Workshop Actions (Ambassador — Complete Within 24 Hours)

| Task | How |
| :--- | :--- |
| Collect post-event Google Form responses (feedback + quote requests) | Via RSVP form shared at event start |
| Submit PoW evidence: attendance photo + headcount screenshot | Via PoW Google Form |
| Follow up with everyone who submitted a quote request | WhatsApp, same-day |
| Post a LinkedIn recap of the workshop (Template 4.3 from Doc_06) | Within 24 hours for maximum reach |
| Send "Thank You" message to the faculty coordinator | WhatsApp/Email next day |
