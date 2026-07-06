# GeneRx AI — Precision Medicine Dashboard

A doctor-facing dashboard that suggests medicines based on symptoms/conditions and compares prices across pharma companies (Crocin vs Dolo vs generic, etc.).

This is a **static, single-file demo** (`index.html`) — no build step, no server required. It runs entirely in the browser with mock/sample data so you can publish it immediately and wire in real data later.

## 🚀 Publish to GitHub Pages (5 minutes)

1. **Create a new repo** on GitHub (e.g. `generx-ai`).
2. **Upload `index.html`** to the root of the repo (drag-and-drop on github.com works, or use git):
   ```bash
   git init
   git add index.html README.md
   git commit -m "Initial GeneRx AI dashboard"
   git branch -M main
   git remote add origin https://github.com/<your-username>/generx-ai.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**.
4. Under "Build and deployment", set **Source: Deploy from a branch**, branch: **main**, folder: **/(root)**.
5. Save. Your site will be live in ~1 minute at:
   ```
   https://<your-username>.github.io/generx-ai/
   ```

## What's included

- **Home dashboard** — stats, quick prediction shortcut, recent predictions, top SHAP-style factors, system overview (matches your original mockup).
- **New Prediction** — pick a condition (Fever, Hypertension, Diabetes, Bacterial Infection, High Cholesterol, Allergy), and get:
  - A suggested generic drug with a mock confidence score
  - A price comparison table across multiple brands/companies, with the **lowest price auto-highlighted**
- Placeholder sections for Patient History, Drug Database, Research Dashboard, Reports, Settings, About — ready to be built out.

## ⚠️ Important — before real clinical/pricing use

- All medicine suggestions and prices in this file are **sample data for demonstration only**. Do not use as-is for real prescribing decisions.
- For real pricing, use public, legal sources rather than scraping retail sites (whose terms typically prohibit it):
  - **NPPA** (National Pharmaceutical Pricing Authority) — official ceiling prices
  - **PMBJP / Jan Aushadhi** — public generic drug price list
- This tool should always be positioned as **decision support**, not a replacement for clinical judgment (see in-app disclaimer).

## Next steps (when you're ready to go beyond static)

- Add **Firebase** (Auth + Firestore) for real patient records and login — works great alongside a static GitHub Pages frontend.
- Build a small **GitHub Actions** job that pulls NPPA/Jan Aushadhi data on a schedule and writes it into Firestore or a JSON file the page reads.
- Replace the mock `conditionMap` in `index.html` with a fetch call to that data source.

Just say the word and I can build the Firebase wiring or the data pipeline next.
