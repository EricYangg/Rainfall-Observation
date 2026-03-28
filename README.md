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
│── data/ # gitignored — created when you run the notebook
│   ├── rainfall_over_nsw/ # extracted model CSVs (+ observed file excluded from combine)
│   └── combined/ # combined CSV and Parquet written by the notebook
│── notebooks/
│   └── 01_data_process_eda.ipynb
│── 525.yml # conda environment (Python + R packages for rpy2 / Task 4)
│── .gitignore
│── README.md
```

## How to Run

1. Create the environment:

   ```
   conda env create -f 525.yml
   conda activate 525_2026
   ```

2. Start Jupyter from the repo (or open the notebook in Cursor/VS Code with this interpreter):

   ```
   jupyter lab
   ```

3. Run `notebooks/01_data_process_eda.ipynb` top to bottom. The notebook assumes it is run with the working directory set to `notebooks/` (the default when you open that folder in Jupyter), so paths resolve to `../data/...`.

The notebook covers **Milestone 1**–style workflow:

* Download `data.zip` via the Figshare API and extract it
* Combine model CSVs into one file with a `model` column (observed file excluded), with optional timing via `@measure`
* Compare memory-aware pandas EDA approaches (dtypes / columns / chunks) with `@measure`
* Export combined data to Parquet and run a short EDA in R through `rpy2` (`arrow`, `dplyr`)