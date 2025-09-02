# WATTs — Workforce Assessment for Transition & Talent

Single‑file, client‑side demo that helps talent assess skills and discover energy career pathways.
This repository contains the **stable v13.1 build** and the **Explorer Mode** add‑on (for non‑energy talent).

> **Privacy by design**: No accounts, no tracking, no server. Everything runs in the browser. Printing and email use the user’s local client (e.g., system print dialog, `mailto:`).

---

## Contents

- `index.html` — **Explorer Mode** demo (additive: keeps original UX/UI)
- `docs/` — design notes and guides mirrored from the client file set (spec, design, changelog, doc guide)
- `legal/` — license files (code + assets), security, support and contributing docs

> _All content herein is sourced from the project’s file set provided by the client. No external sources are used unless explicitly noted._

---

## What is WATTs?

WATTs helps users self‑assess their skills via **Core / Established / Emerging** sections and produces a concise recommendation (General Level, Primary Focus, Upgrades).  

The **Explorer Mode** adds a short, **foundational skills** survey to guide **non‑energy** users toward **Top 3 pathway matches**, with a one‑click “Deep Dive” into the full pathway assessment.

### Key Features

- **Single page**: HTML + CSS + JS in one file for easy hosting.
- **Accessible by default**: Keyboard friendly, ARIA labeling for dialogs and status, device‑agnostic wording.
- **Print‑friendly**: Users can export their results to paper or PDF.
- **Private**: No data leaves the browser.
- **Explorer Mode (add‑on)**: Foundational “building blocks” survey → Top matches → Deep dive into selected pathway.

---

## Quick Start

1. Download this repository (or the HTML files only).
2. Open one of the HTML files directly in your browser:
   - **Explorer demo**: `index.html`
3. Use the pathway selector to run the standard assessment, or press **“Try Explorer Mode”** to test the add‑on.
4. Print or save as PDF from your browser’s print dialog.

> Tip: The app works offline. You can double‑click the HTML file to open it locally.

---

## Explorer Mode (overview)

- Adds a short Likert‑scale survey for **foundational, cross‑pathway “building blocks.”**
- Computes per‑pathway **fit%** from user responses × pathway importance weights.
- Shows **Top 3** matches with “Deep Dive” buttons that open the full pathway assessment (Core / Established / Emerging).  
- Uses **neutral default weights** for all pathways; teams can later refine per‑pathway weights in a small `CROSSWALK` object.

---

## Project Structure

```
/
├─ index.html
└─ legal/
   ├─ LICENSE   (Code license: MIT)
   ├─ ASSETS_LICENSE.md    (Non‑code assets policy)
   ├─ CONTRIBUTING.md
   ├─ SECURITY.md
   ├─ SUPPORT.md
   └─ CODE_OF_CONDUCT.md
```

---

## Accessibility Notes

- Device‑agnostic language (avoid positional cues like “top right”).  
- Descriptive ALT text and ARIA labels on interactive elements (e.g., modal `aria-labelledby`, status `aria-live`).  
- Mobile: Likert labels wrap; results/summary tables are scrollable and use fixed layout to prevent overflow.

---

## Development

Because this is a single‑file app, “development” means editing the HTML (and embedded CSS/JS).

- **Data** lives in a client‑side JSON structure inside the script (`DATA`, plus `FOUNDATION` and optional `CROSSWALK` for Explorer Mode).
- **Builders**: `buildLikert()` renders each section; `collect()` gathers responses; `computeResults()` populates KPIs and recommendations.
- **Explorer Mode** reuses the same builders and adds `renderExplorer()` + `computeExplorerResults()`.

### Local Testing

- Open the HTML file in Chrome/Edge/Firefox/Safari (desktop + mobile).  
- Verify: pathway select, overview modal, section flow, calculate results, print, explore another.  
- For mobile, confirm labels wrap and tables don’t overflow.

### Style & Comments

- Keep functional code unchanged when making documentation edits.  
- Use **HTML comments** for section markers and **JS block comments** for region maps.  
- Follow the **docs/WATTs_Doc_Guide.md** for naming and structural conventions.

---

## Versioning

See **docs/WATTs_Changelog.md**. This repo includes:
- `v13.1` (stable)
- `v13.1_explorer_v0.1` (additive demo)

---

## License

- **Code** is licensed under **MIT** (see `legal/LICENSE`).  
- **Non‑code assets** (text content, datasets, images, PDFs) are **not** covered by the MIT grant and remain the property of their respective owners (see `legal/ASSETS_LICENSE.md`).

---

## Support

If you encounter issues, please check **legal/SUPPORT.md** for contact details and response expectations.
