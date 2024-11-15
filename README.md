# seasonal-icevelocity-prediction

This project aims to predict future ice velocity values for glaciers on the Greenland Ice Sheet (GrIS) using machine learning.

## Project Objectives

The GrIS is losing mass due, in part, to the recent acceleration of many of the outlet glaciers that line the ice sheet’s margins [[1]](https://doi.org/10.1038/s43247-020-0001-2). One of the most dramatic examples of outlet glacier change has been observed at Zachariæ Isstrøm (ZI), one of only three large glaciers comprising the Northeast Greenland Ice Stream (NEGIS), a notable feature of fast-flowing ice that drains ~12% of the ice sheet [[2]](https://doi.org/10.1029/2012GL051634).

In addition to its important role in overall GrIS mass balance, ZI exhibits marked seasonal variability, with flow speeds accelerating in the summer months. Compared to 79N, after the loss of its buffering ice tongue, ZI now calves directly into the ocean, resulting in a dynamic glacier front that changes from seasonal to interannual timescales. This pronounced seasonality provides the opportunity to analyze trends in ZI's velocity fluctuations, predict future trends, and relate external factors to seasonal mass variability. Understanding how seasonality has fluctuated over time and in relation to meltwater and mélange forcing is necessary for attributing ZI’s changing dynamics and accurately predicting future mass loss.

This project has tiers of objectives that will be completed in order:

### Tier 1

- [ ] Predict **annual** velocity values of middle, terminus, and upstream points at ZI 5 years into the future
- [x] Define metric to measure accuracy of prediction

### Tier 2

- [ ] Predict **seasonal** velocity values of middle, terminus, and upstream points at ZI 5 years into the future
- [ ] Compare annual velocity values of ZI with its neighbor, 79N and its middle, terminus, and upstream points
- [ ] Predict annual velocity values along ZI's middle flowline

### Tier 3

- [ ] Incorporate terminus position, temperature, and meltwater discharge into model to improve predictions
- [ ] Predict seasonal velocity values along ZI's middle flowline with >80% accuracy
- [ ] Predict annual velocity values along 79N's middle flowline, compare to ZI

### Tier 4

- [ ] Predict annual velocity values along middle flowlines for 10 Greenland glaciers

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

### 1_download_grimp_veldata

Provides functionality for downloading velocity data from the [Greenland Ice Sheet Mapping Project (GrIMP)](https://nsidc.org/grimp). It currently has functionality for downloading ZI velocity data.

This notebook uses the GrIMP Python API to search for and download 12-day repeat velocity measurements at Zachariæe Isstrøm (ZI).

This notebook draws heavily on code from the [GrIMP Notebooks](https://github.com/fastice/GrIMPNotebooks).

To use this notebook, you must have a NASA EarthData account. The workflow necessary for setting this up for the first time can be found here: [NSIDCLoginNotebook](https://github.com/fastice/GrIMPNotebooks/blob/master/NSIDCLoginNotebook.ipynb).

### 2_clean_data

Remove NaNs and zeroes from the data. NaNs and zeroes are often representative of lapses in data collection or errors in collection and/or processing of raw satellite data. We will optimize the data for ML by removing erreneous data and interpolating to fill in the gaps.

### 3_calculate_statistics

Calculate the mean, median, and variance of the data. Also plot a correlation matrix to analyze the relationship between the data variables. Useful for understanding the distribution of the data before funneling into an ML model and analyzing.

### 4_plot_timeseries

Exploratory data analysis - examples of annual plots, point data extraction, and time series plots generated using the `nisar.VelocitySeries()` raw data and flowlines.

### 5_dimensionality_reduction

Perform dimensionality reduction uisng principal component anlaysis (PCA) on the data to extract features. Use Kmeans clustering to classify the data.

### 6_hyperparam_cv

Perform cross-validation to determine which model predicts most accurately on test and training data based on the mean squared error (MSE) and error plots. Tune the chosen model to determine

## References

1. [Moon, T., Joughin, I., Smith, B., & Howat, I. (2020). 21st-century evolution of Greenland outlet glacier velocities. Science Advances, 6(24), eaaz9541.](https://doi.org/10.1126/sciadv.aaz9541)
2. [Joughin, I., Smith, B. E., Shean, D. E., & Floricioiu, D. (2012). Brief Communication: Further summer speedup of Jakobshavn Isbræ. The Cryosphere, 6(2), 529–531.](https://doi.org/10.1029/2012GL051634)