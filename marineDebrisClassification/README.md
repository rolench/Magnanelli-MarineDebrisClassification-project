This project aims to detect marine debris using satellite imagery from [Sentinel Hub](https://www.sentinel-hub.com/) services and [MARIDA](https://github.com/marine-debris/marine-debris.github.io) dataset.
MARIDA dataset is based on Sentinel-2 satellite images. Here we just consider the ground-truth data (Class and Confidence).
Satellite data are extracted directly thanks to [eo-learn](https://eo-learn.readthedocs.io/en/latest/index.html) library.
We build a Random Forest classifier that performs really well, reaching 0.94 as f1_macro score. 
We also trained the same model with Water Superclass, aggregating some of MARIDA classes into Marine Water, achieving the score of 0.97.

## Contents

- [Installation](#installation)
	- [Installation Requirements](#installation-requirements)
	- [Installation Guide](#installation-guide)
- [Getting Started](#getting-started)
	- [Downloads](#downloads)
	- [Project Structure](#project-structure)
- [References](#references)

## Installation

### Installation Requirements
- python == 3.7.12
- matplotlib == 3.5.2
- numpy == 1.21.6
- pandas == 1.3.5
- seaborn == 0.11.2
- jupyter == 1.0.0
- scikit-image == 0.19.2
- scikit-learn == 1.0.2
- aenum == 3.1.11
- tdqm == 4.64.0
- gdal == 3.4.0
- rasterio == 1.2.10
- shapely == 1.8.0
- fiona == 1.8.20
- sentinelhub == 3.5.2
- eo-learn == 1.0.2
- eo-learn == 1.0.2
- eo-learn-coregistration == 1.0.2
- eo-learn-features == 1.0.2
- eo-learn-geometry == 1.0.2
- eo-learn-io == 1.0.2
- eo-learn-mask == 1.0.2
- eo-learn-ml-tools == 1.0.2
- eo-learn-visualization == 1.0.2

### Installation Guide

The requirement installation is inside the notebook.
Before installing all those packages, consider creating first a new environment:
```bash
conda create --name my_env_name
```
Then activate it, install and launch the notebook from there:
```bash
conda activate my_env_name
```
```bash
conda install notebook
```
```bash
jupyter notebook
```

## Getting Started

### Downloads

You can download the entire MARIDA dataset [here](https://zenodo.org/record/5151941#.Yuf0wWPP23A) or [here](https://mlhub.earth/data/marida_v1). 
Since in this project just class and confidence images are used, these files are uploaded even [here](https://bit.ly/3PQNi4x).
If, for any reason, you want to skip some parts of the notebook, we uploaded also the intermediate results.
[Here](https://bit.ly/3PVTTdH) you can find the EOPatches, [here](https://bit.ly/3OWiApa) the Dataframe and [here](https://bit.ly/3QhtFCf) the classifiers.
The Dataframe must be saved to /data folder.
At the end the structure should be as described below.

### Project Structure

    .
    ├── ...
    ├── data                                      # Main folder that will contain also the Datarframe
    │   └── patches                               # MARIDA patches folder
    │       └── S2_DATE_TILE                      # Unique date-tile folder
    │           ├── S2_DATE_TILE_CROP_cl.tif      # 256 x 256 Classification Mask
    │           └── S2_DATE_TILE_CROP_conf.tif    # 256 x 256 Confidence Level Mask
    ├── eopatches                                 # EOPatch folder
    ├── results                                   # Classifier folder
    └── Marine_debris_detector.ipynb              # Notebook

## References

 > Kikaki K, Kakogeorgiou I, Mikeli P, Raitsos DE, Karantzalos K (2022) MARIDA: A benchmark for Marine Debris detection from Sentinel-2 remote sensing data. PLoS ONE 17(1): e0262247. https://doi.org/10.1371/journal.pone.0262247
