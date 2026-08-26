# WISE-APP Documentation & User Guide

Official documentation for **WISE-APP** (*Weather Impact Simulation and Evaluation for Adaptation Policy and Planning*), an analytical tool designed to stress-test household welfare under historical and projected climate scenarios and evaluate resilience pathways.

## Related Repositories & Links

- **Online Application:** [WISE-APP Online](https://datanalytics-int.worldbank.org/wise-app) *(requires World Bank single sign-on credentials)*
- **R Package:** [worldbank/welfare-weather-app](https://github.com/worldbank/welfare-weather-app)
- **Data Preparation Pipelines:** [worldbank/welfare-weather-app-data](https://github.com/worldbank/welfare-weather-app-data)

## Local Development

This documentation is built with [Quarto](https://quarto.org).

### Preview Locally

```bash
# Preview live documentation in browser
quarto preview
```

### Build HTML Book

```bash
# Render to _book/ directory
quarto render
```

## Deployment to Posit Connect

This repository uses a Git-backed deployment on Posit Connect. When updating documents or configuration, regenerate the deployment manifest:

```r
# In R
rsconnect::writeManifest()
```

## Citation

```
World Bank. 2026. “WISE-APP User Guide: Weather Impact Simulation and Evaluation for Adaptation Policy and Planning.” Available at https://worldbank.github.io/welfare-weather-app-docs/.
```
