# seasonal-icevelocity-prediction

This project aims to predict future ice velocity values for glaciers on the Greenland Ice Sheet (GrIS) using machine learning.

## Project Objectives

The GrIS is losing mass due, in part, to the recent acceleration of many of the outlet glaciers that line the ice sheet’s margins [[1]](https://doi.org/10.1038/s43247-020-0001-2). One of the most dramatic examples of outlet glacier change has been observed at Zachariæ Isstrøm (ZI), one of only three large glaciers comprising the Northeast Greenland Ice Stream (NEGIS), a notable feature of fast-flowing ice that drains ~12% of the ice sheet [[2]](https://doi.org/10.1029/2012GL051634).

In addition to its important role in overall GrIS mass balance, ZI exhibits marked seasonal variability, with flow speeds accelerating in the summer months. Compared to 79N, after the loss of its buffering ice tongue, ZI now calves directly into the ocean, resulting in a dynamic glacier front that changes from seasonal to interannual timescales. This pronounced seasonality provides the opportunity to analyze trends in ZI's velocity fluctuations, predict future trends, and relate external factors to seasonal mass variability. Understanding how seasonality has fluctuated over time and in relation to meltwater and mélange forcing is necessary for attributing ZI’s changing dynamics and accurately predicting future mass loss.

This project has tiers of objectives that will be completed in order:

### Tier 1

- [ ] Predict **annual** velocity values of ZI 10 years into the future
- [ ] Define metric to measure accuracy of prediction

### Tier 2

- [ ] Predict **seasonal** velocity values of ZI 10 years into the future
- [ ] Compare annual velocity values of ZI with its neighbor, 79N

### Tier 3

- [ ] Predict seasonal velocity values of **all Greenland glaciers** 10 years into the future

### Tier 4

- [ ] Incorporate terminus position and meltwater discharge into model to improve predictions

## How to use this repository

1. Use Git to clone the repo:

`git clone https://github.com/UW-MLGEO/MLGEO2024_jensencc`

2. Create and activate a Conda environment

```bash
conda env create -n mlgeo-jensencc -f environment.yml
conda activate mlgeo-jensencc
```

<details>
    <summary>Updating the environment</summary>
To update the environment:

```bash
conda env update -f environment.yml --prune
```

The prune option will uninstall any dependencies that were removed from `environment.yml`.
</details>

## Notebook Descriptions

### download_grimp_veldata

Provides functionality for downloading velocity data from the [Greenland Ice Sheet Mapping Project (GrIMP)](https://nsidc.org/grimp). It currently has functionality for downloading ZI velocity data.

This notebook uses the GrIMP Python API to search for and download 12-day repeat velocity measurements at Zachariæe Isstrøm (ZI).

This notebook draws heavily on code from the [GrIMP Notebooks](https://github.com/fastice/GrIMPNotebooks).

To use this notebook, you must have a NASA EarthData account. The workflow necessary for setting this up for the first time can be found here: [NSIDCLoginNotebook](https://github.com/fastice/GrIMPNotebooks/blob/master/NSIDCLoginNotebook.ipynb).

### plot_timeseries

Examples of annual plots, point data extraction, and time series plots generated using the `nisar.VelocitySeries()` data.

### extract_flowlines

Work in progress. Extract velocity data at flowlines to construct time series of them.
