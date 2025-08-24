# ml-assign-svr-2025
Predictive modelling of 12‑month **death or transplant** after the Norwood procedure in infants with **single‑ventricle congenital heart disease**.  
Machine‑learning comparison of Logistic Regression, Linear SVM, Random Forest and Gradient Boosting using early surgical & ICU metrics from the **Pediatric Heart Network (PHN) SVR public dataset**.

---
## Repo contains
data/
  raw/          # original PHN files (kept local, not committed) 
  R102.csv   # Pre-Norwood
  R103.csv   # Norwood hospitalization
  R301.csv   # Echo Core Lab
  #Other PHN forms exist but were not used in this analysis (e.g., R104, R206 were excluded to prevent data leakage).
  processed/    
figures/        
results/        
 Copy_of_ml-assign-codes-final.ipynb   # consolidated notebook with EDA, preprocessing, models, and evaluation
report/
  Ieee_ML_25011484.pdf # submitted version

## How to reproduce (3 steps)
1. **Install deps** (any Python ≥3.9):  
   `pip install -r requirements.txt`  *(or just use your local env/anaconda)*  
2. **Place data**: download PHN SVR public dataset (see link below) and drop the CSVs in `data/raw/`.  
3. **Run notebooks in order** (00 → 03). Plots auto-save to `figures/`, cleaned CSV to `data/processed/`.

## Data access & acknowledgement
- Download from the Pediatric Heart Network
https://www.pediatricheartnetwork.org/public-use-data-sets/ 
- Required text (also in the report):  
The NIH/NHLBI Pediatric Heart Network Single Ventricle Reconstruction (trial) public dataset was used in preparation of this work. Data were downloaded on 20/07/2025.
*(NIH = National Institutes of Health
NHLBI = National Heart, Lung, and Blood Institute (the NIH institute that funds PHN)*
- Variables used correspond to R102 (Pre-Norwood), R103 (Norwood hospitalization), R301 (Echo Core Lab).


> Raw data are **not** in this repo due to PHN terms. Only derived/cleaned outputs are stored.

## Models compared
- Logistic Regression (baseline)  
- Linear SVM  
- Random Forest  
- Gradient Boosting (HistGradientBoostingClassifier)  
Metrics: Accuracy, ROC‑AUC, Precision/Recall/F1 (weighted). Calibration & confusion matrices included.  
Rejected model discussed: k‑NN (curse of dimensionality, slow) / Deep nets (overkill, low interpretability).
Hyperparameters tuned via cross-validation (details in report §III.C)

## Key figures 
1. Class balance & missingness overview (EDA)  
2. Test-set performance comparison (bar chart: ROC-AUC & accuracy)  
3. Calibration curve for Gradient Boosting  
4. Feature importance (Core vs Extended)
5. Calibration curves included; confusion matrices considered but not shown in final report
   


## License / privacy
- Code: No license, PHN data: subject to PHN Data Use Policy - do **not** redistribute.
- This work is for academic purposes only

## Contact
Sumaiya Rahman (ID: 25011484) • sumaiya2.rahman@live.uwe.ac.uk 
