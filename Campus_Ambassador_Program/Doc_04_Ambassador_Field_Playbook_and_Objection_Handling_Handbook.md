# CarbonPrints – Campus Ambassador Field Playbook & Objection Handling Handbook

**DOCUMENT CLASSIFICATION:** Operational Field Manual / Technical Enablement Guide
**AUDIENCE:** CarbonPrints Campus Ambassadors & Student Fellows
**VERSION:** 2.0 · September 2026 · Upgraded with Real Competition Context & Club Intel

---

## 1. Quick Technical Reference: Engineering Material Selection Matrix

When speaking to engineering students, capstone teams, or club members, speak with **technical authority**. Use this matrix to recommend the right filament for their application — always match material to mechanical requirement, not just cost:

```
┌──────────────────────────────────────────────────────────────────────────────────────────┐
│                        ENGINEERING MATERIAL SELECTION MATRIX                             │
├──────────────┬────────────────────────┬─────────────┬────────────────────────────────────┤
│ MATERIAL     │ MECHANICAL STRENGTH    │ TEMP RESIST │ BEST USE CASES IN STUDENT PROJECTS │
├──────────────┼────────────────────────┼─────────────┼────────────────────────────────────┤
│ PLA          │ High tensile, rigid    │ Up to 55°C  │ Architectural models, aesthetic     │
│ (Standard)   │ (brittle on impact)    │             │ enclosures, rapid fit-checks,       │
│              │                        │             │ presentation prototypes only.        │
├──────────────┼────────────────────────┼─────────────┼────────────────────────────────────┤
│ PETG         │ High toughness, shock  │ Up to 75°C  │ ⭐ Drone arms, snap-fit clips,       │
│ (Engineering)│ resistant, waterproof, │             │ functional robot brackets, gear      │
│              │ semi-flexible          │             │ enclosures, Formula telemetry boxes. │
├──────────────┼────────────────────────┼─────────────┼────────────────────────────────────┤
│ ABS          │ Impact resistant,      │ Up to 95°C  │ ⭐ SAE Baja/Formula engine bay       │
│ (Industrial) │ acetone-smoothable,    │             │ brackets, exhaust-adjacent ducting,  │
│              │ sandable surface       │             │ high-heat sensor housings, jigs.     │
├──────────────┼────────────────────────┼─────────────┼────────────────────────────────────┤
│ TPU (95A)    │ Flexible, rubber-like, │ Up to 80°C  │ ⭐ Robot all-terrain wheels,         │
│ (Elastomer)  │ oil/grease resistant,  │             │ motor vibration dampers, Robocon     │
│              │ indestructible impact  │             │ bumper guards, airtight gaskets.     │
├──────────────┼────────────────────────┼─────────────┼────────────────────────────────────┤
│ CF-PETG      │ Ultra-rigid, chopped   │ Up to 85°C  │ ⭐ Structural drone chassis,         │
│ (Composite)  │ carbon fiber           │             │ high-torque robotic gripper arms,    │
│              │ reinforced, matte      │             │ Formula Bharat steering components.  │
├──────────────┼────────────────────────┼─────────────┼────────────────────────────────────┤
│ ASA          │ UV-stable, weatherproof│ Up to 95°C  │ Outdoor sensor housings, solar       │
│ (Outdoor)    │ similar to ABS         │             │ tracker mounts, weather station      │
│              │                        │             │ enclosures, agri-drone components.   │
└──────────────┴────────────────────────┴─────────────┴────────────────────────────────────┘
```

**Quick Decision Rule:**
* "Will this experience impact forces?" → PETG or CF-PETG
* "Will this be near engine heat?" → ABS or ASA
* "Will this need to flex or absorb vibration?" → TPU 95A
* "Is this just a visual model for a presentation?" → PLA (cheapest)
* "Is this a structural drone or Formula vehicle component?" → CF-PETG (strongest)

---

## 2. Chennai College Competition & Club Calendar (Your Targeting Intelligence)

> **Why This Matters:** Being in the right place at the right time is the difference between 1 order and 10 orders. Study this calendar and **brief yourself 3 weeks before each peak window**.

### Active Competition Teams in the Chennai/TN Region

| Team Name | College | Competition | Type | Key Fabrication Window |
| :--- | :--- | :--- | :--- | :--- |
| **Astral Racing** | Sathyabama Institute of Science & Technology | Formula Bharat / Supra SAE | Combustion vehicle | Oct–Jan (fabrication); Feb (tech inspection) |
| **Camber Racing** | SRM Institute (Kattankulathur) | Formula Bharat | Combustion | Oct–Jan (build); Feb (event) |
| **Shaurya Racing** | VIT Chennai | Formula Bharat, Supra SAE, Formula Imperial | Combustion + EV | Sep–Dec (fabrication sprint) |
| **Raftar Formula Racing Electric** | IIT Madras | Formula Bharat | Electric vehicle | Jun–Nov (design + build) |
| **SRM Team Robocon** | SRM Institute | ABU Robocon / DD Robocon | Robotics | Aug–Jan (design + fabrication) |
| **Various Drone Clubs** | SSN, Rajalakshmi, CEG | Drone racing, DRDO competitions | UAV fabrication | Year-round (season peaks in Nov–Jan) |

> **Ambassador Action:** Identify which of these teams is active at YOUR college or within 2 colleges of yours. Make first contact with the team technical director at the **start of their fabrication window** — not during their competition week.

### Anna University Capstone Project Calendar (Anna University Affiliated Colleges)

| Phase | Period | Ambassador Opportunity |
| :--- | :--- | :--- |
| Project Group Formation & Synopsis | July–August (Semester 7 start) | Introduce CarbonPrints during group formation — become THE resource |
| Phase 1 Internal Review | September–October | First major prototype milestone — many teams need parts fast |
| Phase 2 Internal Review | November (pre-exam) | Second prototype iteration — express orders peak |
| End-Semester Exams | November–December | **Standby Mode** — reduce outreach, maintain relationships |
| Phase 3 / Final Review | February–March | Highest-volume fabrication orders of the year |
| Final Submission & Viva | April–May | Emergency runs + showcase parts for viva tables |

> **The Golden Window:** February–March is the single highest-ROI period for the entire year. Plan to be at maximum campus activation during these 8 weeks.

---

## 3. The 3-Step Client Quoting & File Triage Workflow

Never guess a price. Always guide the student through the standardized 3-step triage pipeline:

```
[ Step 1: File Export ] ────► [ Step 2: Slicing & Quote ] ────► [ Step 3: Production & Dispatch ]
 CAD to STL/STEP (binary)      Grams × Material Rate           10-Printer Farm in Chennai
 Student applies Coupon Code   Transparent Instant Invoice      Porter/Dunzo/Courier dispatch
```

### Step 1: File Export Checklist (Advise the Client)
* **Format:** Always request **`.STL` (Binary, High Mesh Quality)** or **`.STEP / .STP`** format.
* **Dimensional Scale:** Ensure CAD software was set to **Millimeters (mm)**, not inches or meters. (Very common student error.)
* **Wall Thickness:** Functional parts need minimum **1.2 mm** wall thickness (at least 3 perimeter walls on a 0.4mm nozzle).
* **Non-Manifold Check:** Advise student to run "Repair Mesh" in Fusion 360 or use Meshmixer before exporting.
* **Assembly Tolerances:** Mating parts (gears, bearings, press-fits) need +0.2mm clearance built into the CAD — remind them before they export.

### Step 2: Instant Quotation & Discount Application
* Point the student to the CarbonPrints `index.html` workdesk or WhatsApp Desk.
* The quote is derived transparently:
  $$\text{Total Price} = (\text{Grams of Filament} \times \text{Material Base Rate}) + \text{Machine Time Fee}$$
* Remind the client to enter your code (`CP-AMB-XXXX`) to receive **10% instant discount**.
* For Express orders (delivery required within 24 hours): Apply the Express surcharge (quoted separately by operations) and inform the student upfront.

### Step 3: Production Queuing & Delivery Confirmation
* Orders confirmed before **12:00 PM** are queued the same afternoon.
* Standard turnaround: **24 to 48 hours**.
* Express (before 8 PM): Next morning by 9 AM (subject to capacity confirmation).
* Delivery to campus/hostel gate via Porter Genie, Swiggy Genie, or Dunzo.

---

## 4. Objection Handling: The 9 Campus Objections — Word-for-Word Scripts

### Objection 1: "Why pay when our college lab has a 3D printer for free?"

> **The Reality:** Most college lab printers have clogged nozzles, 2-week queues, brittle white PLA, broken Z-axes, and rigid booking windows.
>
> **Your Script:**
> *"College lab printers are great if you have 3 weeks and don't mind brittle white PLA. But if you have a Phase 2 review next Thursday, can you afford a failed print at 11 PM the night before? CarbonPrints runs a dedicated 10-printer farm. We print with ±0.2mm precision, engineering-grade PETG and ABS, and deliver to your hostel gate in 24–48 hours. Plus, 10% off with my student code — the price difference from the lab is usually under ₹200 for most small parts."*

---

### Objection 2: "3D printed parts are too weak — they snap along layer lines."

> **The Reality:** FDM parts are only weak when printed with wrong orientation, insufficient wall count, or low-temperature filament.
>
> **Your Script:**
> *(Pull out the planetary gear showcase print from your Welcome Kit)*
> *"Feel this part. This is printed in PETG with 5 perimeter walls and Gyroid infill — it can take genuine mechanical torque. 3D prints only snap when they're sliced incorrectly. The key is orienting the part so tensile loads run parallel to the layer lines, not perpendicular. CarbonPrints engineers review every STL for print orientation before queuing. And if your part needs flex, we switch to TPU — indestructible under impact. Let me show you how we'd slice your specific part."*

---

### Objection 3: "3D printing is too expensive for our capstone budget."

> **The Reality:** Students assume 3D printing costs thousands because they've seen commercial bureau rates, not local farm rates.
>
> **Your Script:**
> *"Not at all — CarbonPrints is specifically priced for student engineering budgets. A typical robotic sensor bracket or custom gear enclosure costs ₹200 to ₹600 at our rates. Send me your STL file right now on WhatsApp — I'll get you a free sliced quote in 15 minutes so your team knows the exact cost before deciding. No commitment required for the quote."*

---

### Objection 4: "We need this urgently! Our viva is tomorrow at 9 AM."

> **The Reality:** Project teams always procrastinate. This is your highest-value moment — and your highest-margin order.
>
> **Your Script:**
> *"Handled. Send me your STL file right now — I'll flag it to our Chennai farm lead for Priority Express. If your file is in by 8 PM tonight, we'll print through the night and dispatch via Porter/Dunzo so it reaches your college gate by 8:30 AM tomorrow before your viva. Let me get the quote running while you send the file."*
>
> *Then immediately WhatsApp the CarbonPrints operations team: "EXPRESS ORDER — [Name], viva at [Time], parts needed by [Delivery Time]. STL attached. Please confirm capacity."*

---

### Objection 5: "Our design is patent-pending / confidential. What if it leaks?"

> **The Reality:** Capstone teams and hardware startups are genuinely concerned about IP theft — and they're right to be.
>
> **Your Script:**
> *"Completely valid concern. CarbonPrints has a strict corporate IP policy: all client CAD models are assigned an anonymous internal tracking code, stored on offline lab workstations, and permanently deleted after QC sign-off. As an official fellow, I've signed a legally binding NDA. Your file will never be uploaded to public AI tools, shared externally, or published in any form. I can send you the relevant section of our Ambassador Agreement and our production privacy policy if you'd like written confirmation."*

---

### Objection 6: "What if the bearing / motor doesn't fit after printing?"

> **The Reality:** FDM parts shrink slightly on holes due to thermal contraction — a known solvable issue.
>
> **Your Script:**
> *"Great question — this shows you've actually worked with prints before. Our printers are calibrated weekly to ±0.2mm. For tight press-fits and bearing seats, our engineers add the horizontal expansion offset in the slicer before printing. But if there's any genuine dimensional defect or layer separation due to machine error, CarbonPrints has a 100% Free Reprint Guarantee. You have zero financial risk."*

---

### Objection 7: "We don't need a 3D print — we're going to machine it in the college workshop."

> **The Reality:** CNC machine shop time requires skilled operator oversight, booking windows, and can't produce organic geometries or internal channels.
>
> **Your Script:**
> *"Machining is excellent for final metal parts — no argument there. But for your first 3 or 4 prototype iterations, machining is expensive and slow. With 3D printing, you can print a test version in PETG overnight for under ₹500, validate your geometry and tolerances, make CAD corrections, and then commit your design to machining only when you know it's correct. You'll save 60–70% on your total prototyping budget and 2–3 weeks of calendar time."*

---

### Objection 8: "We already use PCBWay / 3Ding / other online vendor."

> **The Reality:** Online vendors from outside Chennai take 5–7 days for delivery and offer no local technical consultation.
>
> **Your Script:**
> *"PCBWay and 3Ding are great for non-urgent parts — no argument there. But if you have a review in 48 hours, they can't help you. CarbonPrints is Chennai-local. We print overnight, and Porter/Dunzo delivers to your campus gate in 45–90 minutes. We're also the only option that gives you a local technical resource — me — who can review your STL file in real-time and flag tolerance issues before you print. We're not competing with them; we're what you use when 7-day shipping isn't an option."*

---

### Objection 9: "The HOD/professor won't allow external vendors for student projects."

> **The Reality:** HODs typically allow students to use external vendors once the vendor has academic or institutional credibility — they just need assurance it's professional.
>
> **Your Script:**
> *"Totally understand — that's actually why I have an official Letter of Appointment on CarbonPrints letterhead with the company CIN number. CarbonPrints also provides a proper tax invoice (GST) for every order, which can be submitted for project budget reimbursement. If it would help, I can prepare a formal introduction letter to your HOD explaining our manufacturing capabilities and quality standards. We've supported Formula Student teams at [reference college if available] through exactly this kind of institutional arrangement."*

---

## 5. Club Partnership Fast Track — The 15-Minute Captain Pitch

> Use this when you get 15 minutes face-to-face with a SAE, Robocon, Formula Bharat, or Drone Club captain or technical director.

**The 3-Object Demo:**
1. **Hand them the planetary gearbox print.** Say: *"Feel how smooth the gear mesh is. That's printed in CF-PETG with ±0.2mm tolerance. This is what we can do for your team components."*
2. **Hand them the material swatch ring.** Say: *"Pick the material that fits your application. I'll explain why each one is suited for different vehicle subsystems."*
3. **Show them the `index.html` quote on your phone.** Say: *"No mystery pricing — here's exactly what a run of 6 suspension brackets in PETG would cost your team."*

**The Club Partnership Offer:**
> *"As a formal Club Manufacturing Partner, your team gets: 15% bulk discount on all seasonal runs, priority queue during your competition fabrication sprint, free DFM consultation on your CAD assemblies, and CarbonPrints logo on your competition vehicle (optional). All I need is 10 minutes with your Technical Director to walk through your component list."*

---

## 6. The Ambassador's Weekly Field Habit System

Follow this 3-node weekly routine to maintain elite performance without disrupting your studies:

```
┌──────────────────────────────────────────────────────────────────────────────────────────┐
│                        WEEKLY AMBASSADOR EXECUTION SYSTEM                                │
├─────────────────┬────────────────────────────────────────────────────────────────────────┤
│ MONDAY (15 min) │ Read WhatsApp Community brief from CarbonPrints. Identify 1 campus     │
│                 │ target this week (a specific team meeting, club session, or lab visit). │
│                 │ Check if any submission reviews are scheduled this week at your college.│
├─────────────────┼────────────────────────────────────────────────────────────────────────┤
│ WEDNESDAY (30m) │ Visit one departmental lab, Baja/Robotics/Drone club workspace, or IDEA│
│                 │ Lab. Bring physical samples. Talk to at least 2–3 peers organically.   │
│                 │ If a team is in crunch mode, offer Express service immediately.         │
├─────────────────┼────────────────────────────────────────────────────────────────────────┤
│ FRIDAY (15 min) │ Submit the week's PoW via the Google Form before 8 PM. Log any leads   │
│                 │ or inquiries in your personal notes. Review the leaderboard update.     │
│                 │ Reply to any pending STL file quote requests from peers.                │
└─────────────────┴────────────────────────────────────────────────────────────────────────┘
```

### Monthly Power Moves (Do These Every 30 Days)
* 🏛️ **Visit one department notice board** and replace old/worn posters with fresh ones.
* 📊 **Check the leaderboard** — identify who is close to a tier boundary and plan 1 targeted activity to push past it.
* 📹 **Create 1 piece of LinkedIn content** — a photo of a peer's finished prototype, a before/after of a design iteration, or a "week in the life of a 3D printing fellow" post.
* 🤝 **Make 1 new club/team contact** — attend one club meeting you've never been to before and introduce yourself organically.

---

## 7. What to Do When Things Go Wrong

| Situation | Your Response |
| :--- | :--- |
| **Print has a defect on delivery** | "I'm so sorry — this is covered by our 100% Reprint Guarantee. I'll flag this to the operations team right now and get a reprint initiated immediately. Can you send me a photo?" |
| **Order is delayed beyond the promised time** | "This is on us. Let me call the operations team right now to get an updated ETA. In the meantime, I'll make sure you get a discount on this order for the inconvenience." |
| **Client is angry about pricing after receiving quote** | "Completely fair — let me see if your part can be optimized to reduce material usage. If we redesign the infill from solid to 15% Gyroid, the price drops by about 30%. Want me to check with our team?" |
| **HOD/Dean bans your poster** | Remove it immediately and without argument. Don't debate with faculty on campus. Explore digital channels (department group, club WhatsApp) instead. |
| **A peer asks for your personal phone to share designs** | "I'd prefer to route it through the official CarbonPrints WhatsApp — that way your design is protected under their NDA and I'm not personally responsible for the file. Here's the link." |
| **You get spammed as a "salesperson" by peers** | Stop promoting in that group immediately. Shift to 1-on-1 conversations. Build trust before any commercial mention. |
