# Rainfall Observation Project

## Overview

This project focuses on working with large-scale climate data to predict daily rainfall in Australia. The dataset consists of outputs from multiple climate models along with observed rainfall values.

## Dataset

The data is sourced from Figshare:

https://figshare.com/articles/dataset/Daily_rainfall_over_NSW_Australia/14096681

The dataset is not stored in this repository. It is downloaded programmatically using the Figshare API.

## Project Structure

```
Rainfall-Observation/
│── data/                 # ignored (downloaded locally)
│── notebooks/
│   └── 01_data_process_eda.ipynb
│── 525.yml              # environment file
│── .gitignore
│── README.md
```

## How to Run

1. Create environment:

   ```
   conda env create -f 525.yml
   conda activate 525_2026
   ```

2. Open the notebook:

   ```
   jupyter lab
   ```

3. Run:
   `01_data_process_eda.ipynb`

This notebook:

* Downloads the dataset using the Figshare API
* Extracts the data
* Prepares it for further analysis

## Notes

* Data (~6GB) is not included in the repository.
* All data processing steps are reproducible via the notebook.
