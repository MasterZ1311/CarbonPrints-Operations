# CarbonPrints – Proof of Work & Commission Tracker Schema

**DOCUMENT CLASSIFICATION:** Operational Tooling & Financial Database Schema
**IMPLEMENTATION PLATFORM:** Google Sheets / Airtable / PostgreSQL
**PURPOSE:** Multi-Tab Architecture for Ambassador Management, Order Attribution, PoW Audits, Monthly UPI Payouts, Certificate Registry, and AARRR KPI Dashboard
**VERSION:** 2.0 · September 2026 · Upgraded with AARRR KPI Tab, Certificate Registry, ASA Material, and Express Order columns

---

## 1. Relational Database & Spreadsheet Architecture

The ambassador tracking system consists of **seven interconnected tables (tabs)** that link ambassadors, tasks, orders, payouts, free material redemptions, credentials, and growth metrics:

```
┌──────────────────────────────────────────────────────────────────────────────────────────┐
│                        RELATIONAL SPREADSHEET ARCHITECTURE (v2.0)                        │
│                                                                                          │
│     [ Tab 1: Ambassador_Master_Roster ] ◄── (Primary Key: Ambassador_ID)                │
│               │                      │                                                   │
│               ├──► [ Tab 2: Proof_of_Work_Submissions ]                                  │
│               ├──► [ Tab 3: Order_Attribution_Ledger ]                                   │
│               ├──► [ Tab 4: Commission_Payout_Ledger ]                                   │
│               ├──► [ Tab 5: Print_Quota_Redemption_Ledger ]                              │
│               ├──► [ Tab 6: Certificate_and_LOR_Registry ]                               │
│               └──► [ Tab 7: AARRR_KPI_Dashboard_Summary ]                               │
└──────────────────────────────────────────────────────────────────────────────────────────┘
```

**Implementation Notes:**
* **Google Sheets:** Free, accessible, sufficient for ≤ 20 ambassadors. Use Google Apps Script for automated alerts.
* **Airtable Free Tier:** Better for ≤ 15 ambassadors with visual Kanban views. Use automations for commission reminders.
* **Airtable Pro / PostgreSQL:** Needed if program scales to 50+ ambassadors with multiple cohorts active simultaneously.

---

## 2. Granular Tab Data Dictionary & Formulas

---

### Tab 1: `Ambassador_Master_Roster`
*The central profile database for all recruited student fellows. This is the source of truth.*

| Column ID | Column Header | Data Type | Formula / Validation / Description |
| :--- | :--- | :--- | :--- |
| `A` | `Ambassador_ID` | String (PK) | e.g., `CP-AMB-001`, `CP-AMB-002`. Format: `CP-AMB-[3-digit sequential]` |
| `B` | `Full_Name` | String | Legal Name from Application Form F-01 |
| `C` | `College_Code` | String | e.g., `SSN`, `IITM`, `CEG`, `VITC`, `SRM-KTR`, `SVCE`, `SATHYA`, `KCG` |
| `D` | `College_Full_Name` | String | Full name e.g., "SSN College of Engineering" |
| `E` | `Department` | String | Mechanical, Mechatronics, Aerospace, ECE, Robotics, etc. |
| `F` | `Academic_Year` | Number | Current study year at time of onboarding |
| `G` | `Graduation_Year` | Number | Expected graduation year e.g., `2027`, `2028` |
| `H` | `WhatsApp_Phone` | Phone Number | 10-digit primary contact — verified at onboarding |
| `I` | `College_Email` | Email | Official .ac.in or .edu.in email |
| `J` | `LinkedIn_URL` | URL | Profile URL — used for post verification |
| `K` | `UPI_ID` | String | e.g., `karthiksubramanian@okhdfcbank` — verified before first payout |
| `L` | `PAN_Number` | String | For TDS compliance (Section 194H if applicable) |
| `M` | `Referral_Code` | String | e.g., `CP-AMB-SSN-KS` — unique, assigned at onboarding |
| `N` | `Onboarding_Date` | Date | Date Agreement signed and kit dispatch authorized |
| `O` | `Tenure_End_Date` | Date | `=N2 + 180` (6 months) |
| `P` | `Cohort_Batch` | String | e.g., `Cohort-1-Q4-2026`, `Cohort-2-Q1-2027` |
| `Q` | `Active_Status` | Enum | `Active` / `Standby` / `Probation` / `Decommissioned` / `Graduated` |
| `R` | `Acquisition_Channel` | String | `LinkedIn` / `Club Captain DM` / `Ambassador Referral` / `Workshop` / `WhatsApp` |
| `S` | `Total_PoW_Points` | Number | `=SUMIF(Proof_of_Work_Submissions!C:C, A2, Proof_of_Work_Submissions!H:H)` |
| `T` | `Total_Order_Points` | Number | `=SUMIF(Order_Attribution_Ledger!E:E, A2, Order_Attribution_Ledger!I:I)` |
| `U` | `Lifetime_Points` | Number | `=S2 + T2` |
| `V` | **`Current_Tier`** | Formula | `=IF(U2>=1500,"Regional Fellow",IF(U2>=500,"Campus Lead","Campus Cadet"))` |
| `W` | **`Commission_Rate`** | Percentage | `=IF(V2="Regional Fellow",0.10,IF(V2="Campus Lead",0.07,0.05))` |
| `X` | `Lifetime_Attributed_Sales` | Currency (INR) | `=SUMIF(Order_Attribution_Ledger!E:E, A2, Order_Attribution_Ledger!G:G)` |
| `Y` | `Total_Commission_Accrued` | Currency (INR) | `=SUMIF(Order_Attribution_Ledger!E:E, A2, Order_Attribution_Ledger!J:J)` |
| `Z` | `Total_Commission_Disbursed` | Currency (INR) | `=SUMIF(Commission_Payout_Ledger!C:C, A2, Commission_Payout_Ledger!F:F)` |
| `AA` | **`Pending_Commission_Payable`** | Currency (INR) | `=Y2 - Z2` |
| `AB` | `Lifetime_Quota_Earned_Grams` | Number | `=IF(V2="Regional Fellow",1500,IF(V2="Campus Lead",700,200))` |
| `AC` | `Quota_Redeemed_Grams` | Number | `=SUMIF(Print_Quota_Redemption_Ledger!C:C, A2, Print_Quota_Redemption_Ledger!F:F)` |
| `AD` | **`Remaining_Quota_Grams`** | Number | `=AB2 - AC2` |
| `AE` | `Workshops_Hosted` | Number | `=COUNTIFS(Proof_of_Work_Submissions!C:C,A2,Proof_of_Work_Submissions!D:D,"CAD Workshop")` |
| `AF` | `Club_Partnerships_Secured` | Number | `=COUNTIFS(Proof_of_Work_Submissions!C:C,A2,Proof_of_Work_Submissions!D:D,"Club Partnership")` |
| `AG` | `Last_Activity_Date` | Date | `=MAXIFS(Proof_of_Work_Submissions!B:B,Proof_of_Work_Submissions!C:C,A2)` |
| `AH` | **`Days_Since_Last_Activity`** | Number | `=TODAY()-AG2` — flags for inactivity monitoring |

**Inactivity Alert Logic (Apply Conditional Formatting):**
* `AH2 > 25` AND `AH2 <= 35` → 🟡 Yellow — trigger Day 25 check-in WhatsApp
* `AH2 > 35` AND `AH2 <= 42` → 🟠 Orange — trigger formal warning notice
* `AH2 > 42` AND `Q2 = "Active"` → 🔴 Red — decommissioning candidate

---

### Tab 2: `Proof_of_Work_Submissions`
*Audit ledger for all non-order activities: workshops, posters, social media, club pitches.*

| Column ID | Column Header | Data Type | Formula / Validation / Description |
| :--- | :--- | :--- | :--- |
| `A` | `Submission_ID` | String (PK) | e.g., `POW-2026-0001` — sequential |
| `B` | `Submission_Date` | Date | Auto-timestamp from Google Form |
| `C` | `Ambassador_ID` | String (FK) | Dropdown linked to `Ambassador_Master_Roster!A:A` |
| `D` | `Activity_Category` | Enum | `Campus Poster` / `WhatsApp Value Post` / `CAD Workshop` / `Club Partnership` / `Social UGC` / `Market Intel` / `IDEA Lab Session` / `14-Day Task A` / `14-Day Task B` |
| `E` | `Activity_Description` | Text | Brief description: location, event name, club name |
| `F` | `Evidence_URL` | Hyperlink | Google Drive link to photo, screenshot, or LinkedIn post URL |
| `G` | `Audit_Status` | Enum | `Pending Review` / `Approved` / `Rejected` — reviewed within 24 hours by Community Lead |
| `H` | **`Points_Awarded`** | Formula | `=IF(G2<>"Approved",0,VLOOKUP(D2,Activity_Points_Lookup!A:B,2,FALSE))` |
| `I` | `Reviewer_Notes` | Text | e.g., "Verified LinkedIn post URL active, 150+ reactions" |
| `J` | `Sprint_Week` | Number | e.g., `1` through `26` — for weekly sprint tracking |

**Activity Points Lookup Table (Create as Named Range or Separate Sheet):**

| Activity Category | Points Awarded |
| :--- | :--- |
| Campus Poster (verified geotagged photo) | 50 pts (max 2/month) |
| WhatsApp Value Post (verified in relevant group) | 30 pts (max 3/month) |
| CAD Workshop (20+ attendees, sheet submitted) | 300 pts |
| AICTE IDEA Lab Session (any format) | 200 pts |
| Club Partnership (Captain confirmation received) | 200 pts |
| Social UGC — LinkedIn (100+ words, company tagged) | 40 pts (max 3/month) |
| Social UGC — Instagram Reel (company tagged, 500+ views) | 60 pts (max 2/month) |
| Market Intel (capstone calendar, department roster) | 75 pts |
| 14-Day Task A (LinkedIn appointment post verified) | 50 pts (one-time) |
| 14-Day Task B (poster or club introduction verified) | 50 pts (one-time) |
| Activation Sprint Complete Bonus (both tasks in 14 days) | 100 pts bonus (one-time) |
| Ambassador Referral (Cohort 2+ — referred candidate completes onboarding) | 200 pts |

---

### Tab 3: `Order_Attribution_Ledger`
*Links all orders from the web workdesk (`index.html`) directly to the referring ambassador.*

| Column ID | Column Header | Data Type | Formula / Validation / Description |
| :--- | :--- | :--- | :--- |
| `A` | `Order_ID` | String (PK) | e.g., `CP-2026-1042` — from `index.html` |
| `B` | `Order_Date` | Date | Date invoice generated |
| `C` | `Client_Name` | Text | Student / Project Team Name |
| `D` | `Client_College` | String | For geographic attribution analysis |
| `E` | `Referral_Code_Used` | String | e.g., `CP-AMB-SSN-KS` |
| `F` | **`Ambassador_ID`** | Formula (FK) | `=IFERROR(VLOOKUP(E2,Ambassador_Master_Roster!M:A,1,FALSE),"UNATTRIBUTED")` |
| `G` | `Material_Used` | Enum | `PLA` / `PETG` / `ABS` / `ASA` / `TPU` / `CF-PETG` / `CF-Nylon` |
| `H` | `Material_Grams` | Number | Sliced weight in grams |
| `I` | `Net_PreTax_Subtotal` | Currency (INR) | Billing before GST and courier charges |
| `J` | `Is_Express_Order` | Boolean | TRUE / FALSE — Express surcharge applies |
| `K` | `Express_Surcharge_INR` | Currency (INR) | `=IF(J2=TRUE, I2*0.25, 0)` — 25% express premium |
| `L` | `Discount_Given_10%` | Currency (INR) | `=I2 * 0.10` |
| `M` | **`Order_Points_Earned`** | Formula | `=ROUNDDOWN(I2 / 100, 0)` *(10 pts per ₹1,000 billed)* |
| `N` | **`Base_Commission_Earned_INR`** | Formula | `=I2 * VLOOKUP(F2,Ambassador_Master_Roster!A:W,23,FALSE)` |
| `O` | **`Express_Commission_Bonus_INR`** | Formula | `=IF(J2=TRUE, I2*0.02, 0)` — additional 2% on Express orders |
| `P` | **`Total_Commission_Earned_INR`** | Formula | `=N2 + O2` |
| `Q` | `GST_Amount_18%` | Currency (INR) | `=(I2 + K2 - L2) * 0.18` |
| `R` | `Payment_Received_Status` | Enum | `Pending` / `Paid via UPI` / `Paid via Bank Transfer` / `Refunded` |
| `S` | `Delivery_Status` | Enum | `Queued` / `Printing` / `QC Passed` / `Dispatched` / `Delivered` |

---

### Tab 4: `Commission_Payout_Ledger`
*Full financial audit trail of all UPI commission disbursements.*

| Column ID | Column Header | Data Type | Description |
| :--- | :--- | :--- | :--- |
| `A` | `Payout_ID` | String (PK) | e.g., `PAY-2026-OCT-001` |
| `B` | `Billing_Cycle` | String | e.g., `October 2026` |
| `C` | `Ambassador_ID` | String (FK) | Links to Master Roster |
| `D` | `Beneficiary_Name` | Text | Student Legal Name |
| `E` | `Beneficiary_UPI` | String | UPI ID from Roster — verify before transfer |
| `F` | **`Gross_Payout_INR`** | Currency | Commission accrued for this cycle |
| `G` | `TDS_Deducted_INR` | Currency | TDS under Sec 194H if applicable (default: 5% above ₹15,000/yr cumulative) |
| `H` | `Net_Payout_After_TDS` | Currency | `=F2 - G2` |
| `I` | `Payment_Method` | Enum | `UPI Direct` / `IMPS Bank Transfer` |
| `J` | `Bank_UTR_Ref_No` | String | 12-digit UPI/UTR Reference — mandatory for audit |
| `K` | `Disbursement_Date` | Date | Date payment processed (must be within 7 business days of month-end) |
| `L` | `Student_Receipt_Ack` | Boolean | TRUE when student confirms receipt via WhatsApp |

---

### Tab 5: `Print_Quota_Redemption_Ledger`
*Prevents farm capacity chaos by tracking ambassador free prototyping allocations.*

| Column ID | Column Header | Data Type | Description |
| :--- | :--- | :--- | :--- |
| `A` | `Redemption_ID` | String (PK) | e.g., `RED-2026-015` |
| `B` | `Redemption_Date` | Date | Date STL file submitted for personal project |
| `C` | `Ambassador_ID` | String (FK) | Links to Master Roster |
| `D` | `Project_Title` | Text | e.g., "Autonomous Robot Gripper Mechanism — Final Year Project" |
| `E` | `Material_Type` | Enum | `PLA` / `PETG` / `ABS` / `ASA` / `TPU` / `CF-PETG` |
| `F` | **`Grams_Sliced`** | Number | Verified sliced weight in grams |
| `G` | `Print_Priority` | Enum | `Normal` / `Rush` (during submission season) |
| `H` | `Farm_Printer_Assigned` | Enum | `Printer 01` to `Printer 10` |
| `I` | `QC_Inspection_Status` | Enum | `Passed ±0.2mm` / `Reprint Required` / `Pending` |
| `J` | `Dispatch_Method` | Enum | `Direct Pickup` / `Porter` / `Courier` |
| `K` | `Dispatch_Tracking_No` | String | Local courier / Porter order ID |

---

### Tab 6: `Certificate_and_LOR_Registry` *(NEW in v2.0)*
*Tracks all issued credentials for verification and audit purposes.*

| Column ID | Column Header | Data Type | Description |
| :--- | :--- | :--- | :--- |
| `A` | `Cert_ID` | String (PK) | e.g., `CP-CA-2026-088` — unique per ambassador per cohort |
| `B` | `Ambassador_ID` | String (FK) | Links to Master Roster |
| `C` | `Cohort_Batch` | String | e.g., `Cohort-1-Q4-2026` |
| `D` | `Issue_Date` | Date | Date certificate issued |
| `E` | `Tier_Achieved` | Enum | `Campus Cadet` / `Campus Lead` / `Regional Fellow` |
| `F` | `LOR_Variant_Issued` | Enum | `B1 (Tier 1/2 Standard)` / `B2 (Tier 3 Strong)` / `None` |
| `G` | `Total_Revenue_Generated` | Currency (INR) | Pulled from Order Attribution Ledger |
| `H` | `Total_Points_Achieved` | Number | Final lifetime points at tenure end |
| `I` | `Workshops_Hosted` | Number | Count from PoW Ledger |
| `J` | `Verification_URL` | URL | `https://verify.carbonprints.in/cert/[Cert_ID]` |
| `K` | `LinkedIn_Credential_Posted` | Boolean | TRUE when LinkedIn post URL submitted |
| `L` | `LinkedIn_Post_URL` | URL | Link to the ambassador's LinkedIn credential post |

---

### Tab 7: `AARRR_KPI_Dashboard_Summary` *(NEW in v2.0)*
*Master growth metrics dashboard reviewed by the Founder every Monday and month-end.*

```
┌──────────────────────────────────────────────────────────────────────────────────────────┐
│                    CARBONPRINTS CAMPUS AMBASSADOR — AARRR KPI DASHBOARD                  │
│                              Auto-calculated from Tabs 1–6                               │
├──────────────────────────────────────────────────────────────────────────────────────────┤
│ ACQUISITION                                                                              │
│ Total Applications Received: =COUNT(Application_Log!A:A)                                │
│ Avg Application Quality Score: =AVERAGE(Application_Log!Score_Column)                   │
│ Selected / Total (Acceptance Rate): =COUNTIF(Active_Status,"Active")/Total              │
├──────────────────────────────────────────────────────────────────────────────────────────┤
│ ACTIVATION                                                                               │
│ Kit Activation Rate (Both Tasks Done / Total Kits Sent): manual input                   │
│ Avg Days to First Commission: =AVERAGEIF(First_Commission_Date, ">0")                   │
│ 14-Day Completion Rate: =COUNTIFS(Task_A_Complete,TRUE,Task_B_Complete,TRUE)/Total       │
├──────────────────────────────────────────────────────────────────────────────────────────┤
│ RETENTION                                                                                │
│ Monthly Active Rate: =COUNTIF(Days_Since_Last_Activity,"<=30")/COUNTIF(Status,"Active") │
│ Ambassadors in Standby: =COUNTIF(Active_Status,"Standby")                               │
│ Ambassadors on Probation (25-42 days inactive): =COUNTIF(AH:AH,">25")-Standby          │
├──────────────────────────────────────────────────────────────────────────────────────────┤
│ REFERRAL                                                                                 │
│ Total Ambassador-Attributed Orders: =COUNTA(Order_Attribution_Ledger!A:A)-1             │
│ Ambassador Revenue Share: =SUM(Attribution!I:I)/Total_Revenue                           │
│ Express Order Rate: =COUNTIF(Order_Attribution_Ledger!J:J,TRUE)/Total_Orders            │
├──────────────────────────────────────────────────────────────────────────────────────────┤
│ REVENUE                                                                                  │
│ Total Campus-Attributed Revenue: =SUM(Order_Attribution_Ledger!I:I) → Target: ₹X/mo    │
│ Total Commission Disbursed: =SUM(Commission_Payout_Ledger!F:F)                          │
│ Commission Payout Ratio: =SUM(Commissions)/SUM(Revenue) → Target: 5–10%                 │
│ Revenue Per Active Ambassador (RPA): =Total_Revenue/Active_Ambassadors                  │
├──────────────────────────────────────────────────────────────────────────────────────────┤
│ FARM IMPACT                                                                              │
│ Total Free Quota Redeemed (Grams): =SUM(Print_Quota_Redemption_Ledger!F:F)              │
│ Farm Capacity Used by Ambassador Quota: =[Total Grams]/[Farm Monthly Capacity]          │
│ Materials Breakdown: COUNTIF by material in Order Attribution Ledger                    │
└──────────────────────────────────────────────────────────────────────────────────────────┘
```

**KPI Thresholds (from Doc_07_AARRR):**

| Stage | KPI | Green | Yellow | Red |
| :--- | :--- | :--- | :--- | :--- |
| Activation | Kit activation rate | > 80% | 65–80% | < 65% |
| Retention | Monthly active rate | > 75% | 55–75% | < 55% |
| Referral | Ambassador revenue share | > 35% | 20–35% | < 20% |
| Revenue | Revenue per active ambassador | > ₹10,000/mo | ₹5,000–₹10,000 | < ₹5,000 |
| Revenue | Commission payout ratio | < 10% | 10–12% | > 12% |

---

## 3. Automated Alerts Setup (Google Apps Script — One-Time Config)

### Alert 1: Day 25 Inactivity WhatsApp Reminder

```javascript
// Runs daily at 9:00 AM via Google Sheets Time-Driven Trigger
function checkInactivity() {
  const sheet = SpreadsheetApp.getActive().getSheetByName("Ambassador_Master_Roster");
  const data = sheet.getDataRange().getValues();
  
  for (let i = 1; i < data.length; i++) {
    const daysSinceActivity = data[i][33]; // Column AH (0-indexed)
    const status = data[i][16]; // Column Q
    const name = data[i][1]; // Column B
    const phone = data[i][7]; // Column H
    
    if (daysSinceActivity >= 25 && daysSinceActivity < 36 && status === "Active") {
      // Trigger WhatsApp notification to Community Lead
      sendWhatsAppAlert(name, phone, daysSinceActivity);
    }
  }
}
```

### Alert 2: Monthly Commission Calculation Reminder

```javascript
// Triggers on the 1st of every month at 10:00 AM
function monthlyCommissionReminder() {
  MailApp.sendEmail({
    to: "operations@carbonprints.in",
    subject: "ACTION REQUIRED: Monthly Ambassador Commission Payout",
    body: "Please calculate and process all pending commissions from Tab 3 and log payouts in Tab 4. Deadline: 7 business days from today."
  });
}
```

---

## 4. Google Forms Integration Schema

### Form 1: Weekly PoW Submission Form (Public, for Ambassadors)

Required fields:
* Ambassador ID (dropdown from master list)
* Activity Date
* Activity Category (dropdown from enum list in Tab 2)
* Activity Description (paragraph text)
* Evidence URL (Google Drive file upload or URL paste)

**On Submit:** Auto-adds row to Tab 2 `Proof_of_Work_Submissions` via Form Response Sheet with `Audit_Status = "Pending Review"`.

### Form 2: Client Order Intake (Embedded in index.html Workdesk)

Required fields:
* Client Name, College Name
* Referral Code Used (text — validated against Referral_Code column in Tab 1)
* Material, Grams (auto-calculated from slicer output)
* Express Order toggle (Y/N)

**On Submit:** Auto-creates row in Tab 3 `Order_Attribution_Ledger` with `Payment_Status = "Pending"`.
