# CarbonPrints Private Limited – Client CRM, Sales & Logistics SOP

## 1. End-to-End Client Order Lifecycle

Every order entering the CarbonPrints ecosystem follows an 8-stage pipeline to guarantee 24–36 hour turnaround across Chennai:

```
[ 1. Inbound Lead ] ──► [ 2. CAD Triage ] ──► [ 3. Quote Issued ] ──► [ 4. Advance / UPI ]
   (WhatsApp/Form)         (Slicing & WT)        (Via index.html)        (Confirmation)
                                                                               │
[ 8. Review & Referral ] ◄── [ 7. Local Dispatch ] ◄── [ 6. QC Gate ] ◄─────── [ 5. Print Farm ]
   (10% Next Order)         (Porter / Genie)        (Caliper Check)       (Queue #01-#10)
```

---

## 2. Lead Qualification & Pricing Protocols

### Step 1: 15-Minute Triage Standard
When a customer sends a file via WhatsApp:
1. **File Check:** Open in Cura/PrusaSlicer. Verify:
   - Is it non-manifold? (Does it have red error walls?)
   - Is it scaled properly? (Frequently students upload in inches or meters instead of millimeters!).
   - Are thin walls under 0.8mm? (Inform client they will not slice with a 0.4mm nozzle).
2. **Quote Generation:** Enter the verified weight and material into [`index.html`](file:///e:/My%20Development/Robohatch-CarbonPrints/index.html).
3. **Dispatch Quote:** Click "Send Quote on WhatsApp" to trigger the pre-formatted commercial breakdown.

### Step 2: Payment Policy
* **Orders under ₹1,000:** 100% payment upfront via UPI before adding to the physical print queue.
* **Orders above ₹1,000 (Startups / Batch Orders):** 50% advance to cover raw filament allocation; remaining 50% settled upon QC photo approval prior to dispatch.

---

## 3. Chennai Local Logistics & Delivery Blueprint

To beat out-of-state competitors (who take 4–6 days), CarbonPrints utilizes Chennai's hyper-local delivery network:

| Delivery Radius | Service Provider | Cost Range | Delivery Speed | Ideal Use Case |
| :--- | :--- | :--- | :--- | :--- |
| **0 – 10 km (Adyar / Guindy / Taramani / Velachery)** | **Swiggy Genie / Dunzo** | ₹40 – ₹90 | 45 – 90 Minutes | Emergency student project parts; quick sample drops to IITM Research Park. |
| **10 – 35 km (Tambaram, KTR, OMR, Ambattur, Avadi)** | **Porter (2-Wheeler)** | ₹90 – ₹180 | 2 – 4 Hours | Standard daytime deliveries across the Chennai metropolitan area. |
| **Bulk Batch Orders (>5 kg)** | **Porter (3-Wheeler Auto / Tata Ace)** | ₹250 – ₹500 | Same Day | Multi-part industrial startup orders or college event batches. |
| **Rest of Tamil Nadu / Outstation** | **India Post (Speed Post) / Delhivery** | ₹50 – ₹90 | 24 – 48 Hours | Coimbatore, Trichy, Madurai student orders. |

---

## 4. Packaging Standard Operating Procedure

3D prints are prone to layer shear if crushed or dropped during two-wheeler courier transit.

```
┌─────────────────────────────────────────────────────────────┐
│                 3D PRINT PACKAGING LAYERS                   │
├─────────────────────────────────────────────────────────────┤
│ Layer 1: Anti-Moisture Zip Pouch (with 1 silica gel bag)    │
│ Layer 2: 2-Layer Air Bubble Wrap (taped securely)           │
│ Layer 3: 3-Ply Corrugated Outer Shipping Box                │
│ Layer 4: Kraft paper or crumpled newspaper void fill        │
│ Layer 5: CarbonPrints Delivery Challan + "FRAGILE" sticker  │
└─────────────────────────────────────────────────────────────┘
```

*Rule:* Never ship delicate 3D prints in flimsy courier poly-bags or thin envelopes. Always use rigid cardboard boxes.

---

## 5. Dispute Resolution & Re-Print Policy

Customer disputes usually fall into two distinct categories:

### Case A: Manufacturing Defect (CarbonPrints Fault)
* **Scenarios:** Delamination/layer splitting, excessive warping, missing features due to slicer error, or under-extrusion.
* **Resolution Protocol:**
  1. Apologize immediately without arguing.
  2. Request a 10-second close-up video of the defect.
  3. Load the file onto the **highest-priority printer queue** and re-print within 12 hours free of charge.
  4. Dispatch express delivery at CarbonPrints' expense.

### Case B: Customer Design Error (Client CAD Fault)
* **Scenarios:** Client provided incorrect motor shaft bore dimensions (e.g., 5.0mm instead of 5.2mm), or model is too weak because client designed 0.5mm structural ribs.
* **Resolution Protocol:**
  1. Measure the printed part with digital calipers on video to prove it matches their uploaded CAD dimensions exactly.
  2. Explain the mechanical constraint politely: *"Your CAD file has a 5.0mm hole, but motor shafts require a 0.2mm clearance allowance."*
  3. Offer a **35% Subsidized Re-print Discount** if they modify their CAD model and re-submit within 24 hours. This turns a frustrated client into a loyal repeat customer.
