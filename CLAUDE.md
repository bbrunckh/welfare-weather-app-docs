# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **Quarto book** project documenting WISE-APP (Weather Impact Simulation and Evaluation for Adaptation Policy and Planning) — a data-driven policy evaluation tool for analyzing how weather and climate affect household welfare. The app itself is a Shiny/R application hosted on Posit Connect; this repo contains only its documentation.

## Commands

```bash
# Load quarto library
library(quarto)

# Preview the book locally with live reload
quarto_preview()

# To stop preview
quarto_preview_stop()

# Build the book to _book/ (HTML output)
quarto_render()

# Render a single chapter
quarto_render("data.qmd")
```

The `_book/` directory is gitignored build output; `.quarto/` is the build cache.

## Architecture

The book documents a three-step analytical workflow:

1. **Model Welfare** (`step1.qmd`) — Fits statistical models relating household welfare outcomes (consumption, poverty) to weather variables using GMD household surveys + ERA5-Land climate reanalysis, linked via H3 spatial indexing.

2. **Simulate Welfare** (`step2.qmd`) — Applies fitted models to historical weather distributions (up to 75 years), CMIP6 future projections (SSP 2-4.5, 3-7.0, 5-8.5), and 10,000-year stochastic catalogs for tail-risk analysis.

3. **Policy Scenarios** (`step3.qmd`) — Evaluates counterfactual adaptation interventions (universal electricity, improved water/sanitation, minimum education) by measuring both direct welfare gains and resilience improvements.

**Data layer** (`data.qmd`) describes the metadata-driven architecture:
- `survey_list.csv`, `variable_list.csv`, `cpi_ppp.csv` control the app UI
- Microdata stored as Parquet files keyed by ISO 3166-1 alpha-3 country codes
- H3 spatial index links household locations to weather hazard data

## Quarto Configuration

[`_quarto.yml`](_quarto.yml) defines the book. Key settings:
- Theme: `cosmo`, output to `_book/`
- Code execution: `freeze: auto` (cached), `echo: true`
- TOC depth 3, numbered sections, collapsible code blocks
- Chapter order: `index.qmd` → `data.qmd` → `step1.qmd` → `step2.qmd` → `step3.qmd`

Custom styles are in [`styles.css`](styles.css).
