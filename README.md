# AR Mutants

This repository contains the dataset and modeling scripts used in the **AR-mutant drug response** study. The project focuses on analyzing and predicting interaction patterns between androgen receptor (AR) mutants and antiandrogen drugs.

---

## 📁 Data

All data files are stored in the `Data/` directory.

- **Public data**: Curated mutant response data from the original study: [osnow/AR_mutant_response](https://github.com/osnow/AR_mutant_response)
- **In-house data**: Includes experimental measurements generated from internal replicates. These data underwent the following preprocessing steps:
  - **Outlier Removal**: For each drug–mutant pair at each dose (8 total replicates: 2 biological × 4 technical), we removed values deviating more than 2 median absolute deviations (MADs) from the median.
  - **Pattern Assignment**: After outlier removal, responses were averaged per dose to form a 7-point dose–response curve. Each curve was labeled based on its overall shape:
    - `up`: strictly increasing
    - `down`: strictly decreasing
    - `mixed`: non-monotonic

---

## 📓 Notebooks

### Data Preparation
- `data_generation.ipynb`: Generates the final dataset by merging public and in-house data, applying feature encoding, and cleaning.

### Modeling (Random Sampling)
- `DNN.ipynb`: Deep neural network training and evaluation using standard random cross-validation.
- `benchmark.ipynb`: Benchmarking using Support Vector Machine (SVM) and Random Forest (RF) with random sampling.

### Modeling (Grouped Sampling)
- `dnn_group_split.ipynb`: Deep neural network with grouped cross-validation (grouped by mutant).
- `benchmark_group_split.ipynb`: Benchmarking using SVM and RF with grouped sampling.

---

## 🔗 Repository

All data and code used in this study are available at:

**[https://github.com/chill-bear/ar_mutants](https://github.com/chill-bear/ar_mutants)**
