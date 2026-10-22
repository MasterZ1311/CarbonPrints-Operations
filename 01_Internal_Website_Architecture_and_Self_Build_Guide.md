# CarbonPrints Private Limited – Internal Website Architecture & Self-Build Roadmap

## 1. Executive Vision: The "Company OS"

An internal office website for an incorporated 3D printing enterprise is an **Operational Operating System (OS)**. It serves as the single source of truth for the Management, Founders, and interns to manage client orders, schedule print queues across 10 machines, monitor spool inventory at ₹4/g, track machine downtime, account for active revenue, and generate compliant commercial tax invoices.

```
┌────────────────────────────────────────────────────────────────────────┐
│                   CARBONPRINTS INTERNAL OPERATIONS OS                   │
├──────────────┬──────────────┬──────────────┬──────────────┬────────────┤
│   MODULE 1   │   MODULE 2   │   MODULE 3   │   MODULE 4   │  MODULE 5  │
│ Order Intake │ 10-Printer   │ Spool & Raw  │ Financials & │ Machine    │
│  & Slicing   │ Farm Queue   │ Material Inv │ Printable    │ Health &   │
│  Quotation   │ & Telemetry  │  Tracking    │ Invoices     │ QC Log     │
└──────────────┴──────────────┴──────────────┴──────────────┴────────────┘
```

---

## 2. Deep Dive: What All to Add to the Internal Website

To run a friction-free operation, your internal site should expand into 6 purpose-built functional modules:

### Module 1: Order Intake, Triage & Quotation Desk (Currently Built in `index.html`)
* **Multi-Part Slicing Configurator:** Ability to log multiple items per client order with individual material, layer resolution (0.28, 0.20, 0.12), infill %, and part weight.
* **Instant Dynamic WhatsApp Quote Generator:** Pre-fills formatted WhatsApp message strings containing part breakdown, turnaround estimate, and UPI payment details.
* **Client Category Tagging:** Tagging orders as *College Project*, *Hardware Startup R&D*, *Automotive Garage*, or *Hobbyist* for historical discounting logic.

### Module 2: 10-Machine Visual Farm Queue & Dispatch Board
* **Visual Slot Kanban:** 10 virtual slots representing Printer 01 through Printer 10.
* **Job Allocation Drag-and-Drop:** Dragging a pending quote into "Printer 04 (ABS)" updates its status to "Printing" with a countdown timer based on estimated print duration.
* **Status Flags:** `Ready / Idle` (Green), `In Progress` (Blue), `Post-Processing` (Purple), `Bed Leveling / Maint` (Yellow), `Error / Thermal Runaway` (Red).

### Module 3: Spool Inventory & Raw Material Consumption Tracker
* **Spool Ledger:** Each 1 kg spool in stock gets a unique internal barcode/ID (e.g., `SP-PLA-04`, `SP-ABS-02`).
* **Auto-Depletion Calculation:** When a 65g PLA print finishes, the website automatically deducts 65g from the active spool.
* **Reorder Trigger Warning:** Flashes a warning banner when total remaining stock of any material (PLA/ABS/TPU) falls below 2 spools (2,000g).
* **Supplier Pricing Benchmark:** Tracks wholesale purchase price per kg from local Chennai vendors (Parrys / Ambattur) to maintain the ₹4/g profitability baseline.

### Module 4: Commercial Invoicing & Delivery Challan Generator
* **A4 Print Engine:** Instant clean-edge, GST/Non-GST tax invoice and packing slip generation.
* **Delivery Challan Mode:** A simplified dispatch slip affixed to courier boxes (Porter, Swiggy Genie) showing sender, receiver, fragile warning, and verification checklist.
* **Payment Status Tracker:** Tracks `Unpaid / Advance Received / Fully Settled via UPI` with screenshot upload or transaction reference ID.

### Module 5: Quality Control (QC) & Failed Print Scrap Log
* **Dimensional Accuracy Checklist:** Interns verify caliper readings (X, Y, Z dimensions within ±0.2mm) before packing.
* **Scrap & Failure Reason Logging:** Whenever a print fails (spaghetti, warping, layer shift, nozzle clog), the intern enters the failed weight and root cause.
* **Farm Failure Rate KPI:** Automatically calculates scrap percentage (`Scrap Grams ÷ Total Grams Consumed × 100`). Target: Under 5%.

### Module 6: Preventive Maintenance & Service Logs
* **Nozzle Life Tracker:** Alerts the operator when a brass nozzle has extruded >5,000g of abrasive filament (ABS/carbon composites).
* **Checklist Scheduler:** Daily bed leveling checks, weekly lead screw lubrication (white lithium grease), and monthly belt tension checks.

---

## 3. How You Can Build & Expand This Yourself (No Budget, Complete Independence)

You do not need to hire expensive web developers or pay monthly SaaS subscriptions ($50–$100/mo) for farm management software like OctoFarms or SimplyPrint. You can build and maintain this system yourself using modern **Local-First Web Technologies**.

### 3.1 Recommended Architecture: "Zero-Cost Local-First PWA"

```
┌─────────────────────────────────────────────────────────────┐
│                    YOUR LOCAL HARDWARE                     │
│   (Laptop / Dedicated Tablet in the 3D Printing Room)       │
├─────────────────────────────────────────────────────────────┤
│  Frontend: Vanilla HTML5 + Clean CSS + Modern JavaScript    │
│  Data Storage: Browser IndexedDB / LocalStorage API        │
│  Backup: 1-Click "Export JSON / CSV to Google Drive"        │
│  Hosting: Free GitHub Pages OR Run locally via file:///     │
│  Network: Zero servers, works 100% offline during outages   │
└─────────────────────────────────────────────────────────────┘
```

#### Why Local-First is Best for CarbonPrints:
1. **₹0 Monthly Hosting Costs:** Free hosting forever via GitHub Pages or simply opening `index.html` on a dedicated laptop in your printing lab.
2. **100% Offline Capability:** Operates even when broadband is down; quotes and invoices can be printed via local Wi-Fi or USB printer.
3. **No Database Configuration Overhead:** Uses the browser’s built-in `IndexedDB` or `localStorage` to save hundreds of order records securely on your machine.
4. **Data Privacy:** Client proprietary CAD files and financial records never leave your local machines.

---

## 4. Step-by-Step Self-Build Roadmap

### Phase 1: Storage Persistence (1–2 Days)
* **Goal:** Make all quotes and orders created in `index.html` save automatically to browser storage so refreshing the page does not lose data.
* **How to implement:**
  - Use `localStorage.setItem('carbonprints_orders', JSON.stringify(orders))` upon clicking "Generate Invoice".
  - Add a "Past Orders History" table at the bottom of the workdesk to search past customer records.

### Phase 2: Farm Queue Kanban (3–5 Days)
* **Goal:** Create a visual grid of 10 printer cards right inside the dashboard.
* **How to implement:**
  - Create an array of 10 printer objects: `{ id: 1, name: "Printer 01", model: "Ender 3", status: "idle", currentJob: null }`.
  - Add buttons on each card: `Assign Current Order`, `Mark Completed`, `Flag Maintenance`.

### Phase 3: Spool Inventory Manager (2–3 Days)
* **Goal:** Track remaining filament weights.
* **How to implement:**
  - Form to enter new spools: Material, Color, Brand, Initial Weight (1000g), Purchase Cost (₹).
  - Deduct weight on print job completion.

### Phase 4: Data Export & Google Sheets Sync (1 Day)
* **Goal:** Ensure the founder has periodic backups for accounting and taxes.
* **How to implement:**
  - Add an **"Export to CSV / Excel"** button that downloads all orders in a format ready for Google Sheets or accounting software (Tally / Zoho).

---

## 5. Free Tools & AI Workflows to Accelerate Development

1. **AI Pair Programming (Antigravity / Gemini / Claude):**
   - You don't need to write JavaScript from scratch. Ask your AI: *"Add an IndexedDB persistence layer to our index.html so order history is saved locally and searchable by phone number."*
2. **VS Code + Live Server Extension:**
   - Free, lightweight IDE. The Live Server extension gives you live auto-reloading as you tweak code.
3. **Browser Developer Tools (`F12`):**
   - Inspect console logs, inspect elements, and test `@media print` layouts in the print emulator.
4. **OctoPrint (Optional Machine Hardware Integration):**
   - If you equip printers with cheap Raspberry Pis or old Android phones running OctoPrint, you can fetch live printer status via simple local REST APIs (`GET /api/printer`) into this internal webpage.
