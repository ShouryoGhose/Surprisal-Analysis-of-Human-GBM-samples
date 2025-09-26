# Surprisal Analysis of Human GBM Samples

This repository contains the codes to run the Surprisal Analysis of Human GBM samples.

**Authors:**  
Shouryo Ghose, Prof. Françoise Remacle, and Prof. Raphael D. Levine.

---

## References
1. F. Remacle, N. Kravchenko-Balasha, A. Levitzki & R. D. Levine,  
   *Information-theoretic analysis of phenotype changes in early stages of carcinogenesis*,  
   **Proc. Natl. Acad. Sci. U.S.A.** 107 (22) 10324–10329 (2010).  
   [https://doi.org/10.1073/pnas.1005283107](https://doi.org/10.1073/pnas.1005283107)

2. S. Zadran, F. Remacle & R. D. Levine,  
   *Surprisal Analysis of Glioblastoma Multiforme (GBM) MicroRNA Dynamics Unveils Tumor-Specific Phenotype*,  
   **PLOS ONE** 9(9): e108171 (2014).  
   [https://doi.org/10.1371/journal.pone.0108171](https://doi.org/10.1371/journal.pone.0108171)

---

## Environment

All codes are written in **Python 3.12**.

### Required Python Libraries
- **NumPy**  
- **Matplotlib**  
- **pandas**  
- **openpyxl** 

Install them with:
```bash
pip install numpy matplotlib pandas openpyxl
```

## Input Files
To download the input files : .

Below is an example of how to do the surprisal analysis of a data set called P1_Peri.
**`P1_Peri.csv`** – Input data matrix  
  - **Columns:** Gene names  
  - **Rows:** Cell IDs.

**`P1_Peri_coordinates.csv`** – XY coordinates of the cells.



---

## Running the Surprisal Analysis

Copy all input files into the desired working directory.

Run the following scripts **in the order listed below**:

1. **`python Do_surprisal.py`**  
   - Main code for performing surprisal analysis.  
   - Transforms the raw data matrix to a **–ln** data matrix and performs **Singular Value Decomposition (SVD)**.  
   - Outputs three Excel files: **`U.xlsx`**, **`Vt.xlsx`**, and **`singular_values.xlsx`**.

2. **`python checksvd.py`**  
   - Checks that the SVD decomposition is correct.

3. **`python computelambda.py`**  
   - Calculates the **Lagrange multipliers (λ)**.  
   - Outputs **`lambda.xlsx`**, where the header contains the Lagrange multipliers and the index column contains the gene names.

4. **`python plotconstraint.py`**  
   - Plots the **steady state (G₀)** and **eight constraints (G₁–G₈)** in a **3 × 3 figure** using coordinates from `ordered_barcode_coordinates.csv`.

5. **`python plotconstraintcustomrange.py`**  
   - Same as above but plots the steady state and constraints using a **custom color-bar scale range (–0.04 to +0.04)**.


