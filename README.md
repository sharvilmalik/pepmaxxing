# pepmaxx

**The Peptide Research Database** — [pepmaxx.xyz](https://pepmaxx.xyz)

A free, open research aggregation tool indexing 56 peptide and peptide-adjacent compounds with evidence grading, interaction data, and curated stacks.

## What's Inside

- **Compound Database** — 56 compounds graded A–D on evidence quality
- **Head-to-Head Compare** — Side-by-side comparison of any two compounds
- **Interaction Checker** — Published interaction data for compound pairs
- **Stack Finder** — Goal-based compound matching from the literature
- **5-Tab Detail Modals** — Overview, Benefits, Studies (PubMed), Clinical Trials (ClinicalTrials.gov), Safety

## Data Sources

- PubMed peer-reviewed studies (with PMIDs)
- ClinicalTrials.gov registered trials (with NCT IDs)
- FDA regulatory filings and FAERS data
- Expert commentary (Huberman Lab, Peter Attia, etc.)
- Published research protocols

## Run Locally

```bash
npx serve public -l 3000
```

Then open http://localhost:3000

## Deploy to Vercel

```bash
vercel --prod
```

Or connect this repo to Vercel and it auto-deploys on push.

## Tech

Single self-contained HTML file — no build step, no dependencies, no framework. All CSS, JS, and data inline. Designed to be fast, portable, and zero-maintenance.

## Legal

This is a research aggregation tool, not a medical resource. Nothing on this site constitutes medical advice. See full disclaimer on site.
