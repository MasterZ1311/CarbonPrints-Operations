# Campus Ambassador Application Schema & Candidate Screening Rubric

**DOCUMENT CLASSIFICATION:** Recruitment Infrastructure & HR Screening System
**OPERATIONAL PURPOSE:** Candidate Intake, Automated Scoring, and Interview Script
**VERSION:** 2.0 · September 2026 · Upgraded with AARRR Acquisition Stage Research

---

## 1. Acquisition Strategy Context (AARRR Stage 1)

> **Read First:** This form schema is the primary **Acquisition Funnel instrument** for the CarbonPrints Ambassador Program. The goal is NOT to maximize the number of applications — it is to attract the highest-quality candidates from the right engineering colleges, departments, and clubs.
>
> **Target Quality Benchmark:** Prefer 40 well-qualified applications over 200 generic ones. Every screening layer in this document is intentionally calibrated to filter for students with existing campus social capital in the engineering maker ecosystem.

---

## 2. Ideal Candidate Profile (ICP) — The "Perfect Ambassador"

Before evaluating any application, internalize this persona:

```
┌──────────────────────────────────────────────────────────────────────────────────────────┐
│                      CARBONPRINTS IDEAL CAMPUS AMBASSADOR PERSONA                        │
├──────────────────────────────────────────────────────────────────────────────────────────┤
│ YEAR:      2nd or 3rd year undergraduate (peak campus social capital, low placement       │
│            pressure, 2+ semesters of remaining tenure for ROI).                          │
│                                                                                          │
│ DEPARTMENT: Mechanical / Mechatronics / Aerospace / Automobile Engineering (primary).    │
│             ECE, EEE with robotics/IoT focus (secondary).                                │
│             CS/IT with hardware club involvement (conditional).                          │
│                                                                                          │
│ CLUB ROLE: Active member or officer in SAE Baja, Formula Bharat, Robocon, Drone Club,    │
│            IEEE Robotics Section, AICTE IDEA Lab student committee, or Maker Space.      │
│                                                                                          │
│ TECH LEVEL: Has used at least one CAD tool (SolidWorks, Fusion 360, CATIA, OnShape).    │
│             Understands what an STL file is. Has seen or used a 3D printer.             │
│                                                                                          │
│ PERSONALITY: Proactive self-starter. Communicates well in English and Tamil.            │
│              Has 500+ LinkedIn connections or growing LinkedIn presence.                  │
│              Known and trusted by at least 2 academic departments.                       │
│                                                                                          │
│ RED FLAGS:  1st year with no club involvement. 4th year with placement deadlines.        │
│             CS student with zero hardware interest. < 2 hours/week available.           │
└──────────────────────────────────────────────────────────────────────────────────────────┘
```

---

## 3. Public-Facing Application Form Schema (Tally.so / Google Forms)

This schema defines the fields, validation constraints, and intent behind the public application form used to recruit student ambassadors across target colleges.

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                         APPLICATION INTAKE FORM ARCHITECTURE                           │
├───────────────────┬───────────────────┬──────────────────────┬─────────────────────────┤
│ PART 1:           │ PART 2:           │ PART 3:              │ PART 4:                 │
│ IDENTIFICATION    │ CAMPUS INFLUENCE  │ TECHNICAL AFFINITY   │ SCENARIO & PITCH        │
│ • Contact Info    │ • Clubs & Roles   │ • CAD Tools Used     │ • Viva Emergency Pitch  │
│ • College / Dept  │ • Student Cohorts │ • Prototyping Exp    │ • Time Commitment       │
│ • LinkedIn URL    │ • Active Projects │ • Materials Known    │ • Personal Motivation   │
└───────────────────┴───────────────────┴──────────────────────┴─────────────────────────┘
```

### Form Fields Specification

| Field ID | Field Label | Input Type | Required | Validation / Placeholder | Intent & Analysis |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `F-01` | Full Legal Name | Text (Single-line) | **Yes** | e.g., "Karthik Subramanian" | Official verification |
| `F-02` | University / College Name | Dropdown / Text | **Yes** | Select from Tier 1/2 list or specify | Geolocation and tier triage |
| `F-03` | Engineering Department / Major | Dropdown | **Yes** | Mech, Mechatronics, Aero, ECE, CS, etc. | Filters for target departments |
| `F-04` | Current Academic Year | Radio | **Yes** | 1st Year / 2nd Year / 3rd Year / 4th Year | Prioritizes 2nd and 3rd years |
| `F-05` | Student Registration / Roll No. | Text (Single-line) | **Yes** | e.g., "312221104055" | Verifies active student status |
| `F-06` | WhatsApp Mobile Number | Phone Number | **Yes** | 10-digit Indian Mobile (+91) | Primary communication line |
| `F-07` | College Email Address (.edu / official) | Email | **Yes** | e.g., "karthik.s@ssn.edu.in" | Academic domain validation |
| `F-08` | LinkedIn Profile URL | URL | **Yes** | Must include "linkedin.com/in/..." | Evaluates professional presence & network size |
| `F-09` | Campus Club Memberships & Roles | Multi-select + Text | **Yes** | SAE/Baja, Formula Bharat, Robocon, Drone Club, IEEE, Rotaract, AICTE IDEA Lab | Identifies distribution hubs |
| `F-10` | Are you an office-bearer or core team member of any club? | Radio + Text | **Yes** | Yes (specify role) / No | Differentiates leaders from passive members |
| `F-11` | CAD & 3D Modeling Proficiency | Checkboxes | **Yes** | SolidWorks, Fusion 360, CATIA, Blender, OnShape, None | Gauges technical foundation |
| `F-12` | Describe your 3D printing or hardware prototyping experience | Text (Paragraph) | Optional | 50–100 words (projects built or observed) | Distinguishes makers from tourists |
| `F-13` | **The 48-Hour Viva Emergency Scenario** | Text (Paragraph) | **Yes** | *See scenario prompt below* | Tests problem-solving & sales tact |
| `F-14` | Have you heard of or used CarbonPrints before? | Radio + Text | **Yes** | Yes (how) / No | Existing brand awareness signal |
| `F-15` | Weekly Bandwidth Available | Radio | **Yes** | < 2 hrs / 2–4 hrs / 4–6 hrs | Filters out undercommitted candidates |
| `F-16` | Why do you want to be a CarbonPrints Campus Fellow? | Text (Paragraph) | **Yes** | 100–150 words. What specifically makes you want to represent us — not a generic answer. | Filters resume-padders from genuine candidates |
| `F-17` | Upload Student ID Card (Front) | File Upload (PDF/IMG) | **Yes** | Max 5MB | Fraud prevention and academic verification |
| `F-18` | How did you hear about this program? | Dropdown | **Yes** | LinkedIn / Founder DM / Club Captain / WhatsApp / College Workshop / Other | Attribution tracking for Acquisition channel analysis |

---

### Key Scenario Question (Field `F-13`):
> **Scenario Prompt:**
> *"It is 48 hours before the Mechanical Department Capstone Project Viva. A final-year project team needs 4 custom robotic drone gear arms 3D printed immediately, but their college lab printer has a clogged nozzle and a 10-day queue. They are stressed and considering laser-cutting acrylic instead. What would you do and say to triage their design, recommend the right 3D printing material, and route their order to CarbonPrints?"*

**What a Strong Answer Looks Like:**
* Empathizes first ("I totally understand — let me help you fix this right now")
* Asks technical questions (What material? What are the load requirements? How tight is the tolerance on the gear teeth?)
* Correctly identifies that acrylic is wrong for gear arms (brittle, planar stress only)
* Recommends PETG or CF-PETG with high wall count and Gyroid infill for gear teeth
* Promises a realistic timeline (24 hrs) and mentions the CarbonPrints Express option
* Uses their referral code to offer the 10% student discount

---

## 4. Acquisition Channel Attribution

Add `F-18` data to the `Ambassador_Master_Roster` Tab to track which acquisition channels yield the highest-scoring candidates over time. AARRR Acquisition target benchmarks:

| Channel | Target % of Applications | Target Quality Score |
| :--- | :--- | :--- |
| Founder LinkedIn Post | 35–40% | > 70/100 avg |
| Direct Club Captain DM | 25–30% | > 75/100 avg |
| Current Ambassador Referral | 10–15% (from Cohort 2+) | > 72/100 avg |
| Campus Workshop | 15–20% | > 65/100 avg |
| WhatsApp Group | < 10% | < 60/100 avg |

> **Action:** If WhatsApp yields > 30% of applications with low quality scores, redirect effort to LinkedIn outreach and club captain DMs.

---

## 5. 100-Point Candidate Screening Rubric

Applications are evaluated using this 100-point rubric. Candidates with scores ≥ 75 proceed directly to the 10-minute vetting call.

```
┌────────────────────────────────────────────────────────────────────────────────────────┐
│                   CANDIDATE SCORING BREAKDOWN (100 PTS)                                │
├───────────────────────────────────────┬──────────────┬─────────────────────────────────┤
│ EVALUATION DIMENSION                  │ WEIGHT (PTS) │ BENCHMARK TARGET                │
├───────────────────────────────────────┼──────────────┼─────────────────────────────────┤
│ 1. Campus Network & Social Capital    │ 35 Points    │ Core club exec / team captain   │
│ 2. Technical & Prototyping Literacy   │ 25 Points    │ Active CAD user / maker         │
│ 3. Scenario Pitch & Problem Solving   │ 25 Points    │ Empathetic, technical, speedy   │
│ 4. Motivation & Commitment Quality    │ 10 Points    │ Specific, non-generic answer    │
│ 5. Academic Year & Availability       │ 5 Points     │ 2nd or 3rd year, 2–4+ hrs/week │
└───────────────────────────────────────┴──────────────┴─────────────────────────────────┘
```

### Detailed Scoring Breakdown

**1. Campus Network & Social Capital (Max 35 Points):**
* *30–35 pts:* President, Captain, or Core Office-Bearer of SAE Baja, Formula Bharat, Robocon, Formula Student, Drone Club, or Student Council. OR: LinkedIn profile has 1,000+ connections with engineering content.
* *20–29 pts:* Active core team member of an engineering design team; regular participant in maker/tech fests with photographic evidence.
* *10–19 pts:* General student with good peer relations and club membership but no formal leadership responsibilities.
* *0–9 pts:* Isolated student with no club affiliations or visible campus engagement. No LinkedIn presence.

**2. Technical & Prototyping Literacy (Max 25 Points):**
* *22–25 pts:* Actively designs in Fusion 360/SolidWorks/CATIA; understands infill, layer height, wall count, print orientation, and material properties (PLA vs. PETG vs. TPU vs. CF composites). Has 3D printed something.
* *14–21 pts:* Basic CAD familiarity; understands what an STL file is; eager to learn slicers. Has watched/observed a 3D printer.
* *5–13 pts:* Knows what 3D printing is but has never CAD modeled anything. Limited technical vocabulary.
* *0–4 pts:* Zero CAD experience; does not understand additive manufacturing basics.

**3. Scenario Pitch & Problem Solving (Max 25 Points):**
* *22–25 pts:* Clear, empathetic, technically specific response. Correctly explains acrylic's failure mode for gear arms; recommends PETG/CF-PETG with specific reasoning; mentions 24-hr turnaround; offers student code discount. Shows urgency management.
* *14–21 pts:* Recommends CarbonPrints but offers limited technical justification. Misses material recommendation specifics.
* *7–13 pts:* Generic answer. Says "I'd forward the order" without demonstrating understanding of the client's design or urgency.
* *0–6 pts:* One-sentence or completely wrong answer. Shows lack of initiative, technical awareness, or commercial sensitivity.

**4. Motivation & Commitment Quality (Max 10 Points):**
* *9–10 pts:* `F-16` answer is specific to CarbonPrints' manufacturing capability, the Chennai engineering ecosystem, or their personal project needs. Mentions a specific project or competition they're working on.
* *5–8 pts:* Moderate specificity. Mentions the LOR, commission, or prototyping credits but in a genuine way.
* *0–4 pts:* Generic ("I want to gain experience in marketing"). Copy-paste feeling answer. No mention of why CarbonPrints specifically.

**5. Academic Year & Availability (Max 5 Points):**
* *5 pts:* 2nd or 3rd year with 2–4+ hours/week available. Not in final placement semester.
* *3 pts:* 1st year with unusually strong club involvement. OR 4th year in a non-placement stream.
* *0 pts:* Less than 2 hours/week available. 4th year with active placement season.

### Cutoff Action Rules

| Score | Action | Timeline |
| :--- | :--- | :--- |
| **≥ 80 Points** | Fast-Track Candidate — direct invitation to vetting call | Within 24 hours of application review |
| **65–79 Points** | Normal Pool — vetted if target college slot is open | Within 48–72 hours |
| **< 65 Points** | Polite automated rejection + invite to student maker community waitlist | Automated within 24 hours |

---

## 6. The 10-Minute Telephonic / Google Meet Vetting Script

**INTERVIEWER:** Founder or Community Lead
**CANDIDATE:** Shortlisted Student Applicant
**TOTAL DURATION:** 10 Minutes — stick to time out of respect for the student

### Phase 1: Rapid Icebreaker & Rapport (Minutes 00:00 – 01:30)
> *"Hi [Name], this is [Your Name] from CarbonPrints Private Limited. We reviewed your campus ambassador application for [College Name], and your background with [Club Name / CAD experience / specific detail from application] really stood out to us. How are classes going this week — any major reviews or submissions coming up?"*

### Phase 2: Campus Ecosystem Assessment (Minutes 01:30 – 04:30)
> *"Tell me about the hardware and fabrication scene at [College Name]. When final-year teams, Baja/Formula teams, or club teams need mechanical parts or prototypes, what is their current workaround? Where do they go?"*

**Listen For:**
* Lab printer downtime, 2-week queues, brittle PLA, clogged nozzles.
* Frustration with PCBWay/3Ding's 5–7 day shipping.
* Awareness of AICTE IDEA Lab at their college (green flag).
* Knowledge of specific capstone review dates (advanced green flag).

**Green Flag:** Candidate names specific professors, lab technicians, competition deadlines, or club budgets.
**Red Flag:** "I don't know — I haven't really paid attention to that."

### Phase 3: Situational Readiness Check (Minutes 04:30 – 07:30)
> *"If we send you our physical Welcome Kit with industrial-grade mechanical 3D prints and your personalized referral posters tomorrow, what is the very first step you would take on campus this week?"*

**Listen For:** Direct, specific action steps. Examples of strong responses:
* "I'll show the planetary gear to our Baja chassis team captain tomorrow at our Wednesday club meeting."
* "I'll get HOD permission to put up posters in the Mech block — I know the department coordinator."
* "I'll message the Formula Bharat team captain directly — I already know him."

**Red Flag:** Vague answers ("I'll just post it in some WhatsApp groups").

### Phase 4: Commitment Alignment & Next Steps (Minutes 07:30 – 10:00)
> *"As a CarbonPrints Campus Fellow, you'll earn 5% to 10% cash commission via UPI, free 3D printing credits for your own projects, and an executive Letter of Recommendation. In return, we need 3–4 hours a week of focused engagement, weekly PoW submissions, and attendance at monthly virtual community calls. There are no classroom deadlines — your exams always come first. Does this align with your semester workload?"*
>
> *"Do you have any questions for me?"*
>
> *"Excellent. We're finalizing Cohort 1 selections by Friday. If selected, your formal Letter of Appointment and Ambassador Agreement will arrive via email within 24 hours. You'll need to sign and return it before we ship your kit. Looking forward to building something great together at [College Name]!"*

---

## 7. Post-Interview Vetting Scorecard Template

```
┌──────────────────────────────────────────────────────────────────────────────────────────┐
│                          POST-VETTING CALL SCORECARD                                     │
├──────────────────────────────────────────────────────────────────────────────────────────┤
│ Applicant Name:   ___________________________  Date: ____________                        │
│ College:          ___________________________  Dept: ____________                        │
│ Interviewer:      ___________________________  Duration: ________                        │
├──────────────────────────────────────────────────────────────────────────────────────────┤
│ CALL PERFORMANCE                                                                         │
│ [ ] High energy & natural communicator — would own a room at a club meeting              │
│ [ ] Deep relationship with departmental clubs / team captains                            │
│ [ ] Genuine CAD / 3D printing passion — spoke from experience not theory                 │
│ [ ] Realistic, specific understanding of weekly time commitment                          │
│ [ ] Identified first concrete action step immediately                                    │
├──────────────────────────────────────────────────────────────────────────────────────────┤
│ CONCERNS / RED FLAGS NOTED:                                                              │
│ _______________________________________________________________________________          │
│ _______________________________________________________________________________          │
├──────────────────────────────────────────────────────────────────────────────────────────┤
│ COLLEGE SLOT STATUS: [ ] Open slot at this college  [ ] Already has an ambassador        │
├──────────────────────────────────────────────────────────────────────────────────────────┤
│ Final Decision:  [ ] APPROVED FOR ONBOARDING  [ ] RESERVE LIST  [ ] DECLINED            │
│                                                                                          │
│ If Reserve: Reason for reserve (not rejected):                                           │
│ _______________________________________________________________________________          │
└──────────────────────────────────────────────────────────────────────────────────────────┘
```

> **Reserve List Policy:** Candidates placed on the Reserve List must be notified within 48 hours with a message acknowledging their strong performance and explaining they are Priority Reserve for the next available cohort slot. Do NOT communicate as a rejection.

---

## 8. Red Flag Disqualifiers (Override Any Score)

Even a high-scoring candidate should be **immediately disqualified** if any of the following are observed:

| Red Flag | Why It Disqualifies |
| :--- | :--- |
| Claims to be "an influencer" with large follower counts but zero engineering content | Audience mismatch — their reach is irrelevant to our ICP |
| Works part-time (restaurant, retail, delivery) while at college | Time bandwidth is genuinely unavailable — will ghost |
| Is applying to 5+ other ambassador programs simultaneously | Will dilute attention; treat us as a resume line item |
| Cannot name a single specific club, professor, or student lab at their college | Not actually embedded in the campus maker ecosystem |
| Is recommended by a current ambassador but has applied without any research | Referral quality must still pass independent rubric screening |
