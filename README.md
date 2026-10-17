# Salvage It — Universal Industrial Recovery Intelligence

> **Tagline:** Recover value. Reduce waste.

**Salvage It** is an industrial decision-support platform that helps businesses determine the safest, most practical, and economically sensible way to recover value from damaged, defective, surplus, unused, obsolete, or decommissioned physical items.

The central question answered by the platform is:

> **“What is the best way to recover value from this item?”**

Depending on the item, the answer might be to reuse it, redeploy it, resell it, inspect it, repair it, refurbish it, repurpose it, harvest its spare parts, sell it as scrap, recycle its constituent materials, or dispose of it appropriately.

---

## 1. Key Features

- **Radically Simplified UI**: Clean, uncluttered dark-mode interface (`#0B0F14` page background, `#111821` panels, `#171F2B` cards, `#293442` borders, `#67C7F5` accent). A new user understands what the app does within seconds.
- **Easy 4-Step Assessment Workflow**:
  - **Step 1 — Identify the item**: Item name, category, quantity, material (if known), optional photo and description.
  - **Step 2 — Describe its condition**: Unused/surplus, used and functional, damaged/defective, obsolete/decommissioned, or unknown. Targeted follow-ups only when relevant.
  - **Step 3 — Add costs and value (optional)**: Replacement value, repair/inspection costs, transport. Never treats missing values as zero.
  - **Step 4 — Get a recommendation**: One clear primary recommendation, why it is appropriate, estimated net recovery value, and what to check before proceeding.
- **Results Screen Answers 4 Core Questions**:
  1. *What should I do with this item?*
  2. *Why is this the recommended option?*
  3. *How much value might I recover?*
  4. *What should I check before proceeding?*
  - Initial view shows at most 3 alternative recovery routes. Detailed mathematical comparisons and what-if sensitivity sliders are cleanly tucked inside an expandable **View detailed analysis** section.
- **Fully Editable & Removable Demo Data**:
  - Pre-seeded with 6 realistic fictional demo cases (surplus gaskets, unused bolts, leaking valve, scaffolding, motor, controller PCB).
  - Clearly tagged as **Demo data**.
  - Every demo case can be edited, duplicated, or deleted.
  - Users can clear all demo data with a single action and confirmation dialog.
  - Deleted demo cases are permanently remembered and not automatically resurrected on page reload.
  - Demo cases can be restored anytime via Settings without affecting user-created assessments.
- **Streamlined 6-Destination Navigation**:
  1. **Dashboard** — overview of assessed items, potential recovery value, and items needing attention.
  2. **Assess an Item** — the primary workflow for evaluating an item and deciding what to do with it.
  3. **Inventory** — items being tracked, including their condition, quantity, and current status.
  4. **Assessment History** — previously completed assessments, with options to open, edit, duplicate, or delete them.
  5. **Materials** — the reference library for materials and recovery options.
  6. **Reports** — recovery value, item outcomes, and waste reduction summaries.
  - Settings accessible via a small gear icon. Currency converter in the top bar.
- **USD Default with Live 18-Currency Exchange Matrix**:
  - USD baseline across all dashboards and economic comparisons.
  - Supports: USD, EUR, GBP, INR, JPY, CNY, CHF, CAD, AUD, NZD, SGD, HKD, KRW, AED, SAR, BRL, MXN, ZAR.
  - Live rates fetched with automatic caching, source attribution, last-updated timestamps, and fallback resilience.
  - Preserves historical exchange rate snapshots with every assessment.
- **Hard Safety & Engineering Constraints**:
  - Pressure equipment requires API 598 hydrostatic testing before reuse.
  - Scaffolding requires EN 12811 / OSHA competent-person inspection.
  - Critical structural fasteners cannot be reused if yielded or corroded.
  - Electronic assemblies require certified WEEE/RoHS specialist recovery.
- **Server-Side Gemini AI Integration**: Integrates Google Gemini (`gemini-3.8-flash`) via an Express server-side proxy route (`/api/gemini/analyze`) to inspect uploaded photographs, analyze nameplates, and identify materials without exposing API keys to the browser.
- **Data Export**: Export inventory and master assessment ledgers to CSV or generate clean printable reports.

---

## 2. Technology Stack

- **Frontend**: React 19, TypeScript, Tailwind CSS v4, Lucide Icons.
- **Server**: Node.js, Express, `tsx` runtime, Vite middleware mounting in development mode (`server.ts`).
- **AI SDK**: `@google/genai` (version 2.4.0) executed exclusively on the server side.
- **Storage**: Client-side localStorage persistence with separate tracking for demo vs user data.

---

## 3. Local Development

```bash
# Install dependencies
npm install

# Start development server on port 3000
npm run dev
```

Visit `http://localhost:3000` in your browser.

### Building for Production
```bash
# Build frontend bundle
npm run build

# Start production server
npm run start
```
