# sentinel-notebooks
Reusable Sentinel workflows for notebook-based geospatial analysis.

This repository provides reference notebooks and Python scripts for common Earth observation tasks: data discovery, download, preprocessing, spectral index generation, and quick-look visualization.

While current examples include wildfire mapping, the same workflow can support other application domains such as LEAF toolbox vegetation analysis, disturbance monitoring, and environmental change assessment across Sentinel missions.

## Data source alignment

These notebooks are intended to work well with the Sentinel Products Canada Mirror:
https://registry.opendata.aws/sentinel-products-ca-mirror/

This mirror is Canada's value-add contribution to the Sentinel community. The data is curated for Canadian applications and is intended to complement the radarsat-notebooks repository for multi-mission workflows.

## Why this repository is useful

1. Reproducible analysis
- End-to-end processing is documented in notebooks and scripts so methods can be rerun consistently across AOIs and dates.

2. Flexible spectral workflows
- The code is structured so index generation can be adapted for different phenomena (for example NBR/BAI2 for fire, NDVI and related metrics for vegetation-focused workflows).

3. Quality control visibility
- Intermediate outputs (masks, bands, thumbnails, derived rasters) can be inspected to catch cloud contamination, scene mismatch, and AOI issues early.

4. Path to operationalization
- Notebook logic is paired with script-based automation patterns, making it easier to move from exploration to repeatable processing.

## Repository at a glance

- data/: reference geospatial inputs used by examples.
- examples/: notebook demos for Sentinel processing patterns.
- dNBR_Calculate_py/: scripts for NBR and differenced NBR style processing.
- external_stac_api/: scripts that use external STAC APIs for scene retrieval and analysis.
- external_stacAPI_example/: notebook example using external STAC access.
- fire_operationalization_py/: automation example for event-driven processing (currently fire oriented, reusable as a pattern).

## Getting started

1. Clone the repository.
2. Create and activate a Python virtual environment.
3. Install dependencies for the workflow you want to run (for example in fire_operationalization_py/requirements.txt).
4. Open a notebook in examples/ or external_stacAPI_example/ and run cells step by step.
5. Adapt index logic, thresholds, and outputs for your target application (fire, LEAF-style vegetation monitoring, or another Sentinel use case).

## Example entry points

- Notebook demo: [examples/Sentinel2_Jun2025_FlinFlonDenareBeach_FireDemo.ipynb](examples/Sentinel2_Jun2025_FlinFlonDenareBeach_FireDemo.ipynb)
- STAC notebook demo: [external_stacAPI_example/FireAlgorithmVerify_Download.ipynb](external_stacAPI_example/FireAlgorithmVerify_Download.ipynb)
- Automation scripts: [fire_operationalization_py/README.md](fire_operationalization_py/README.md)

## Notes

- Existing fire-specific scripts remain available and unchanged.
- Future additions can include domain-focused examples (for example LEAF toolbox workflows) while sharing the same core Sentinel processing pipeline.
