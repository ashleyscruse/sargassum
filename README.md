# AI-Enhanced Remote Sensing for Caribbean Sargassum Monitoring

We are building a system to detect, track, and predict Sargassum bloom arrivals along Dominican Republic coastlines using satellite imagery and machine learning. This project is in its early stages. We are currently recruiting student researchers.

## The Problem

Massive Sargassum seaweed blooms have increasingly impacted Caribbean coastlines, disrupting ecosystems, tourism, and coastal livelihoods. Current monitoring relies on coarse satellite products with limited spatial resolution and no forecasting for local decision-makers.

## Research Phases

| Phase | Aim | Proposed Approach |
|-------|------|-------------------|
| **Detection** | Identify Sargassum in satellite imagery | Spectral index methods (FAI, AFAI, NDVI), potentially UNet segmentation or CNN classification |
| **Tracking** | Model where blooms are moving | Lagrangian particle tracking using ocean current and wind data, possibly optical flow |
| **Prediction** | Forecast when blooms will reach DR coastlines | Sequence modeling (LSTM or Transformer), ensembled with physical drift models |
| **Dashboard** | Make predictions accessible to coastal managers | Web-based mapping interface with a prediction API |

Methods will be refined as we begin working with the data. What's listed above reflects our starting direction, not final architecture decisions.

## Current Status

This project is in pre-project setup. See [STATUS.md](STATUS.md) for detailed progress.

## For Students

We are recruiting student researchers (1 at Yale, 1 at Morehouse). See [CONTRIBUTING.md](CONTRIBUTING.md) for what you'll work on and what we expect.

## Data Sources

We plan to work with the following. Access is not yet set up for all sources.

| Source | Data | Resolution |
|--------|------|------------|
| Sentinel-2 | Multispectral imagery | 10m, 5-day revisit |
| MODIS | Ocean color, SST | 250m to 1km, daily |
| Landsat 8/9 | Multispectral imagery | 30m, 16-day revisit |
| HYCOM | Ocean current fields | 1/12 degree, daily |
| ERA5 | Wind and atmospheric reanalysis | 0.25 degree, hourly |

## Project Structure

```
sargassum/
├── data/
│   ├── raw/              # Satellite imagery
│   ├── labeled/          # Training labels, ground-truth from fieldwork
│   └── external/         # Ocean currents, wind, atmospheric data
├── pipeline/
│   ├── ingest/           # Data download and organization
│   └── preprocess/       # Atmospheric correction, cloud masking, spectral indices
├── models/
│   ├── detection/        # Sargassum identification models
│   ├── tracking/         # Bloom drift modeling
│   └── prediction/       # Arrival forecasting
├── dashboard/            # Web interface and prediction API
├── fieldwork/            # Collection protocols, site documentation
├── notebooks/            # Exploration, analysis, visualization
├── docs/                 # Architecture decisions, onboarding
└── scripts/              # Utility scripts, HPC job submission templates
```

## Team

| Person | Affiliation | Role |
|--------|-------------|------|
| Ashley Scruse | Morehouse College | Technical Lead |
| Xuhui Lee | Yale University | Co-PI, remote sensing and atmospheric modeling |
| Kinnis Gosha | Morehouse College | Co-PI, project oversight |
| Whitney Nelson | Morehouse College | Research Scientist, dashboard and stakeholder engagement |

## Infrastructure

- **Compute.** TACC HPC (Vista) through Morehouse Supercomputing Facility
- **Languages.** Python
- **Libraries.** To be determined as we begin development. Likely PyTorch and standard geospatial tools.

## Acknowledgments

This work is supported by the ASCEND program. Compute resources provided by the Texas Advanced Computing Center (TACC) through the Morehouse Supercomputing Facility.
