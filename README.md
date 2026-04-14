# Selective Self-Consistency: A Confidence Gate for TTC on Small Reasoning Models

Submission to the IJCAI-2026 Workshop on **Small-Scale Foundation Models**.

Uses the standard ACL 2024 LaTeX template (see
[`README-template.md`](./README-template.md) for the original template
instructions).

## What's in this repository

- `latex/acl_latex.tex` — paper source (8 pages + appendix).
- `latex/custom.bib` — bibliography.
- `latex/figures/` — four publication figures.
  - `fig1_oracle_retention.png` — headline: oracle retention across 12 experiments.
  - `fig2_pareto_pooled.png` — TTC-Gate Pareto curves (pooled $n{=}400$).
  - `fig3_fp16_vs_q4.png` — greedy / SC / BoN bar grid.
  - `fig4_operating_points.png` — operating points with $1\,000\times$ bootstrap CI.
- `latex/acl.sty`, `latex/acl_natbib.bst`, `latex/acl_lualatex.tex` — ACL 2024
  template files (unmodified).

## Build

```bash
cd latex
pdflatex acl_latex
bibtex  acl_latex
pdflatex acl_latex
pdflatex acl_latex
```

## Key findings

- Oracle TTC-gate strictly dominates always-SC on **12/12** experiments
  (retention 109–174%).
- On Qwen-Q4 × MATH-500, always-SC is **3 pt worse** than always-greedy.
- A 12-feature logistic gate saves **45–99% compute** at ≥98% accuracy
  retention with tight skip-rate CIs.
- All experiments run on a single MacBook M4 Pro using MLX; ≈ 7.5 GPU-hours total.

## Template provenance

ACL 2024 LaTeX template (`acl.sty`, `acl_natbib.bst`) adapted by Steven
Bethard, Ryan Cotterell, Rui Yan from earlier ACL / NAACL proceedings; see
[acl-org/acl-style-files](https://github.com/acl-org/acl-style-files).
Template files are unmodified apart from our paper source and figures.
