# Campus Ambassador Program – Complete Requirements & Launch Readiness Checklist

**VERSION:** 2.0 · September 2026 · Upgraded with AICTE IDEA Lab Colleges, AARRR Context & 25-Point Checklist

## Purpose & Scope

Launching a high-impact, professional Campus Ambassador Program requires establishing clear operational rails **before** recruiting students. Attempting to recruit ambassadors without the underlying operational infrastructure leads to communication breakdown, phantom sign-ups, unfulfilled promises, and brand erosion.

This document outlines the **exhaustive, foundational requirements** across six critical operational pillars needed to build, launch, and govern a world-class student ambassador network.

> **AARRR Context:** This document primarily governs the **Acquisition** and **Activation** stages of the CarbonPrints AARRR growth funnel (see `07_AARRR_Growth_Metrics_Framework.md`). Every pillar below directly enables a high-quality first-mile experience for both ambassadors and their campus peers.

---

```
┌───────────────────────────────────────────────────────────────────────────────────────┐
│                       THE 6 FOUNDATIONAL LAUNCH PILLARS                               │
├──────────────────────────┬──────────────────────────┬─────────────────────────────────┤
│ 1. STRATEGIC & COHORT    │ 2. DIGITAL TOOLING &     │ 3. INCENTIVES & BUDGET          │
│    • Charter & Goals     │    TRACKING INFRASTRUCTURE│    • Swag & Welcome Kits       │
│    • Target Campus Tiers │    • Attribution Coupons │    • Free Prototyping Quotas    │
│    • Ideal Candidate ICP │    • CRM & PoW Portal    │    • Commission & LOR Matrix    │
├──────────────────────────┼──────────────────────────┼─────────────────────────────────┤
│ 4. LEGAL & GOVERNANCE    │ 5. ENABLEMENT & CONTENT  │ 6. OPERATIONAL CADENCE          │
│    • Ambassador Agreement│    • Master Field Manual │    • Weekly Sync Schedule       │
│    • Client IP / NDA     │    • Workshop Pitch Decks│    • Core KPIs & Milestones     │
│    • Anti-Spam Rules     │    • Objection Cheat-Sheet│   • Offboarding Protocols       │
└──────────────────────────┴──────────────────────────┴─────────────────────────────────┘
```

---

## Pillar 1: Strategic & Cohort Architecture Requirements

Before publishing an application link, the program's structural boundaries must be codified:

### 1.1. Program Charter & Core Mission
* **Primary Objective:** Build an organic, student-led distribution channel that establishes CarbonPrints as the default rapid prototyping and 3D printing destination across premier engineering colleges.
* **Secondary Objectives:**
  * Source high-volume final-year capstone projects, formula student/robotics club manufacturing runs, and drone/IoT hardware prototypes.
  * Identify and groom top engineering and leadership talent for internal operations and engineering apprenticeships.
  * Host technical CAD/DFM (Design for Additive Manufacturing) workshops on campuses to elevate local maker culture.

### 1.2. Campus Tiering & Geographic Focus
Categorize target colleges into 3 distinct operational tiers to focus management bandwidth:

* **Tier 1 (Anchor Hubs — High Hardware Density):** Elite engineering institutions with active Formula Bharat/Baja/Robocon teams, AICTE IDEA Labs, funded fabrication labs, and high capstone project density.
  * **Priority Targets:** IIT Madras (Raftar Formula Racing Electric), Anna University CEG/MIT, SRM Kattankulathur (Camber Racing, SRM Team Robocon), SSN, VIT Chennai (Shaurya Racing), Sathyabama (Astral Racing).
  * **AICTE IDEA Lab Colleges in Tier 1:** KCG College Karapakkam, SRM Easwari, SRM Valliammai.
  * *Deployment:* 2 Ambassadors per campus (1 Technical Lead for clubs/projects + 1 Community Lead for student outreach).

* **Tier 2 (Growth Hubs — Project Heavy):** Established private engineering colleges with large Mech/Mechatronics/Aerospace cohorts. Strong capstone culture, less active competition teams.
  * **Priority Targets:** Rajalakshmi Engineering, St. Joseph's, Crescent, Jerusalem College Pallikaranai (AICTE IDEA Lab), SVCE Sriperumbudur (AICTE IDEA Lab), VISTAS, Loyola-ICAM.
  * *Deployment:* 1 Ambassador per campus.

* **Tier 3 (Emerging Hubs):** Regional technical colleges, polytechnics, and architecture/design institutions.
  * *Deployment:* 1 Ambassador per campus. Conditional on ICP match — only if a strong candidate applies.

### 1.3. Ideal Candidate Persona (ICP) & Eligibility Criteria
Not all students make effective ambassadors. Recruitment criteria must filter for:
* **Academic Standing:** 2nd or 3rd-year undergraduate students (1st-year students lack campus network; final-year students are overwhelmed with placements/exams).
* **Target Disciplines:** Mechanical Engineering, Mechatronics, Robotics & Automation, Aerospace, EEE/ECE, Product Design, Architecture, or Computer Science (with hardware/IoT interest).
* **Campus Influence:** Members of SAE collegiate clubs (Baja, Supra, Formula Bharat), IEEE/Robotics clubs, Drone societies, or Department Student Association office-bearers.
* **Core Competencies:** Basic familiarity with CAD (Fusion 360, SolidWorks, Tinkercad), active presence on LinkedIn and campus WhatsApp networks, excellent peer communication skills.

---

## Pillar 2: Digital Tooling & Tracking Infrastructure Requirements

To keep administrative overhead under 4 hours per week for company leadership, automated operational tooling must be set up:

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                     MINIMAL ZERO/LOW-COST OPERATIONAL STACK (v2.0)                     │
├───────────────────────┬─────────────────────────────────┬──────────────────────────────┤
│ FUNCTION              │ RECOMMENDED PLATFORM            │ PURPOSE                      │
├───────────────────────┼─────────────────────────────────┼──────────────────────────────┤
│ 1. Application Portal │ Tally.so / Google Forms         │ Frictionless intake          │
│ 2. Community Hub      │ Discord or WhatsApp Community   │ Daily chat, briefings        │
│ 3. Attribution Engine │ Internal Workdesk `index.html`  │ Custom referral promo codes  │
│ 4. Proof of Work (PoW)│ Google Sheets + Apps Script     │ Auto-alerts, task auditing   │
│ 5. CRM & Tracker      │ Airtable (free) / Google Sheets │ 7-tab ambassador database    │
│ 6. Brand Asset Hub    │ Canva Pro + Google Drive        │ Posters, Reels, LinkedIn kits│
│ 7. Digital Signature  │ DocuSign / DigiLocker Verify    │ Agreement execution          │
│ 8. UPI Payouts        │ HDFC/ICICI Business Banking     │ Commission disbursement      │
│ 9. Verification Site  │ Vercel/Firebase Static Page     │ cert verification QR codes   │
└───────────────────────┴─────────────────────────────────┴──────────────────────────────┘
```

### 2.1. Unique Attribution & Coupon Architecture
* Each ambassador is assigned an unchangeable attribution ID:
  `CP-AMB-[COLLEGE CODE]-[AMBASSADOR INITIALS]` (e.g., `CP-AMB-SSN-SK`).
* **The Dual-Value Hook:**
  * *For the End Client:* 10% instant discount on their 3D printing invoice.
  * *For the Ambassador:* 5% to 8% cash commission or equivalent 3D printing credit, logged automatically upon invoice generation in `index.html`.

### 2.2. Proof of Work (PoW) Submission Pipeline
Ambassadors must submit empirical evidence for non-order tasks:
* Mandatory weekly form with 3 upload fields:
  1. Screenshot of approved campus WhatsApp group announcement or Discord post.
  2. Photo of physical notice board poster or club orientation meeting.
  3. Lead capture details (Name, Department, Expected Prototype Delivery Date, CAD file link).

---

## Pillar 3: Incentives, Rewards & Budgetary Requirements

Ambassadors must receive rapid, tangible value. The incentive system combines **material utility, social status, cash, and career progression**.

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                        THE 4-TIER INCENTIVE ARCHITECTURE                               │
├──────────────────────┬──────────────────────────────┬──────────────────────────────────┤
│ CATEGORY             │ IMMEDIATE REWARD             │ MILESTONE-BASED UNLOCK           │
├──────────────────────┼──────────────────────────────┼──────────────────────────────────┤
│ 1. Material Hardware │ Physical Welcome Showcase Kit│ 250g Free Print Quota per 10k INR│
│                      │ with exotic 3D printed parts │ of verified campus orders        │
├──────────────────────┼──────────────────────────────┼──────────────────────────────────┤
│ 2. Direct Financial  │ N/A (prevents phantom signups│ 5% Direct Cash via UPI on all    │
│                      │                              │ referred paid orders             │
├──────────────────────┼──────────────────────────────┼──────────────────────────────────┤
│ 3. Career & Academic │ Official Letter of Appointmt │ Verifiable LOR signed by Director│
│                      │ for LinkedIn & resume        │ + Priority summer internship slot│
├──────────────────────┼──────────────────────────────┼──────────────────────────────────┤
│ 4. Social & Status   │ Official Ambassador Badge &  │ "Campus Ambassador of the Month" │
│                      │ ID card lanyard              │ feature on CarbonPrints LinkedIn │
└──────────────────────┴──────────────────────────────┴──────────────────────────────────┘
```

### 3.1. Physical Welcome & Showcase Kit Specifications
Before speaking to peers, ambassadors must hold physical proof of industrial 3D printing quality in their hands:
* **The Welcome Kit Box Contents:**
  1. *Laminated Official Ambassador ID Card & Branded Lanyard.*
  2. *The "Tolerance & Capability" Showcase Piece:* A functional 3D printed mechanical assembly (e.g., Planetary Gearbox or Multi-Color Gyroid in PLA/TPU) demonstrating tight tolerances (±0.2mm).
  3. *Material Sample Swatch Ring:* Small branded swatches showing PLA, ABS, PETG, TPU (flexible), and Carbon Fiber PETG.
  4. *Sticker Pack:* Premium die-cut laptop stickers ("Powered by CarbonPrints", "Additive Ninja").
  5. *5x A3 Printed Posters:* Ready for department notice boards with custom QR code.

---

## Pillar 4: Legal, Governance & Risk Safeguards

Protecting the company from legal liability, IP disputes, and brand damage requires explicit contractual agreements:

### 4.1. Student Ambassador Agreement (Core Terms)
* **Independent Representative Clause:** The student is an honorary brand ambassador and an independent representative. They are **not** an employee, contractor, or commercial agent of CarbonPrints Private Limited, and possess no authority to bind the company legally.
* **Pricing & Commitment Integrity:** Ambassadors cannot offer arbitrary pricing, promises of zero-cost re-prints, or commit the company to delivery deadlines without written confirmation from lab operations.
* **Zero Client CAD Distribution (Strict NDA):** In the course of their duties, ambassadors may collect STL/CAD files from fellow students. Ambassadors are legally bound to upload files strictly to the designated CarbonPrints portal and must never copy, modify, distribute, or reverse-engineer client IP.
* **Anti-Spam & Harassment Policy:** Zero-tolerance policy for spamming unofficial university groups, mass messaging without consent, or posting offensive material. Violations result in immediate termination and revocation of credentials.

---

## Pillar 5: Training, Enablement & Content Assets

Equipping students with professional assets ensures uniform messaging and builds immediate confidence:

### 5.1. The Master Ambassador Field Handbook (SOP)
A concise 10–12 page guide containing:
* Additive manufacturing 101 (FDM basics, print orientations, infill densities, layer heights).
* File preparation guidelines for clients (STL, OBJ, STEP, 3MF formats).
* Standard turnaround times, shipping rules (Porter, Dunzo, India Post), and packaging guarantees.
* FAQ and objection handling scripts (e.g., "Why not just use the college lab printer?" Answer: College labs have 2-week backlogs, broken nozzles, and zero filament choices; CarbonPrints delivers within 24–48 hours with industrial dimensional tolerance).

### 5.2. Ready-to-Deliver Campus Presentation Decks
* A standardized, branded 25-slide deck: *"Rapid Prototyping & Industrial 3D Printing: From CAD Model to Working Prototype"*.
* Allows ambassadors to host a sanctioned 45-minute technical seminar inside their college mechanical/robotics department with zero prep stress.

---

## Pillar 6: Program KPIs & Operational Cadence

To guarantee positive return on investment, monitor a concise dashboard:

### 6.1. Primary Performance Indicators (KPIs)
1. **Ambassador Activation Rate:** Percentage of inducted ambassadors who generate at least 1 verified inquiry within 14 days of receiving their kit (Target: >75%).
2. **Campus Inflow Revenue:** Total gross billing generated through assigned coupon codes per campus per month (Target: ₹15,000–₹40,000/campus/month during project seasons).
3. **Club Partnerships Secured:** Official prototyping partnership agreements signed with campus robotics, Baja, or Formula Student teams.
4. **Content & Awareness Velocity:** Number of physical posters deployed, college WhatsApp blitzes executed, and LinkedIn student prototype tags.

### 6.2. Weekly & Monthly Governance Cadence
* **Monday Morning (Asynchronous Sprint Briefing):** 3-minute video/text brief posted in the Discord/WhatsApp community detailing the week's focal challenge (e.g., "This week: Connect with 3rd-year Mechatronics project leads").
* **Friday Evening (PoW & Lead Submission Cutoff):** Automated submission reminder for weekly proof-of-work.
* **Monthly All-Hands (45 Minutes):** Virtual showcase featuring:
  * Monthly revenue leaderboard and top ambassador recognition.
  * Direct product roadmap preview from CarbonPrints engineering team.
  * Guest masterclass on DFM, mechanical prototyping, or startup building.

---

## 7. Master Launch Readiness Checklist

Use this 25-point checklist to verify complete launch readiness before opening public applications. All items must be ✅ before any ambassador application link is published.

**PHASE 1 — STRATEGIC FOUNDATION**
```
[ ] 01. Program Charter finalized: goals, AARRR targets, management time budget (< 4 hrs/week).
[ ] 02. Target Campus List compiled: Tier 1 (8–10), Tier 2 (10–15), Tier 3 (optional).
[ ] 03. ICP (Ideal Candidate Profile) approved and shared with screening team.
[ ] 04. Cohort launch date and semester-aligned recruitment campaign calendar locked.
[ ] 05. SWOT analysis reviewed (Doc_05_SWOT) and key strategic risks noted.
```

**PHASE 2 — LEGAL & GOVERNANCE**
```
[ ] 06. Student Ambassador Agreement (v2.0, Doc_01) reviewed by company counsel.
[ ] 07. Digital signature mechanism (DocuSign / PDF + WhatsApp confirmation) operational.
[ ] 08. TDS & PAN collection process confirmed with company accountant.
[ ] 09. Client CAD confidentiality and NDA policy embedded in Agreement and Playbook.
[ ] 10. Anti-spam protocol documented and linked from Agreement (Doc_01, Section 5.1).
```

**PHASE 3 — INFRASTRUCTURE & TOOLING**
```
[ ] 11. Application form (Tally.so / Google Forms) with F-01 to F-18 fields live and tested.
[ ] 12. Ambassador attribution code schema integrated into quotation desk `index.html`.
[ ] 13. 7-tab Google Sheets / Airtable CRM operational (Doc_07 schema implemented).
[ ] 14. PoW submission form connected to Tab 2 of the CRM (auto-populates on submit).
[ ] 15. Google Apps Script inactivity alert configured (25-day and 42-day triggers).
[ ] 16. UPI commission payout workflow and monthly cycle SOP approved.
[ ] 17. Express Order surcharge (25%) and Express Commission Bonus (2%) configured in workdesk.
[ ] 18. Certificate verification URL (verify.carbonprints.in) set up and tested with dummy cert.
```

**PHASE 4 — CONTENT & ENABLEMENT**
```
[ ] 19. Physical Welcome Kit produced: lanyard, ID card, planetary gearbox showcase, swatch ring, 5x A3 posters.
[ ] 20. Canva Brand Kit with poster templates, LinkedIn post frames, and Instagram Reel frames uploaded to Drive.
[ ] 21. Ambassador Field Playbook (Doc_04) exported to PDF and added to Shared Drive.
[ ] 22. 25-slide DFAM Workshop Deck (Doc_05) exported to PowerPoint + PDF in Drive.
[ ] 23. All outreach script templates (Doc_06) formatted in Canva-ready copy-paste card format.
[ ] 24. LOR templates (Doc_08, Variants B1 and B2) in letterhead-formatted PDF format.
[ ] 25. AARRR KPI Dashboard (Tab 7, Doc_07) formulas verified and green/yellow/red thresholds set.
```

---

## 8. Next Step in Documentation Sequence

To inspect how the ambassador lifecycle, tiered rewards, and task economy operate in real-time, proceed to:
* [`03_Ambassador_Lifecycle_Incentives_and_Governance_Model.md`](file:///e:/My%20Development/Robohatch-CarbonPrints/Company_Operations_OS/Campus_Ambassador_Program/03_Ambassador_Lifecycle_Incentives_and_Governance_Model.md): The day-to-day operational execution manual.
