README - AI/ML Surrogate Modeling for Binary Distillation
------------------------------------------------------

This package contains the files for the AI/ML surrogate modeling task for 
binary distillation (Ethanol-Methanol system at 1 atm).

Contents:
---------
1. distill_data.csv  - Dataset (1200 data points, cleaned and validated)
2. main.ipynb                      - Jupyter Notebook with data preprocessing, model training, 
                                     evaluation, diagnostics, and plots
3. AI_Distillation_Surrogate_Report.pdf - Final report (3–5 pages) with results and conclusions
4. README.txt                      - This file

Dataset Description:
--------------------
Inputs (X):
- R       : Reflux ratio (0.8 – 5.0)
- xF      : Feed mole fraction of light key (0.20 – 0.95)
- F_mol_s : Feed flowrate (±30% around 27.78 mol/s)

Outputs (y):
- xD      : Distillate mole fraction of light key (purity)
- Qreb_kW : Reboiler duty (kW)

Data Splitting:
---------------
- Training + Validation: All data except R in [3.5, 4.5]
- Test: Block split (R in [3.5, 4.5]) for extrapolation evaluation
- Validation set: 30% of training block

Models Implemented:
-------------------
- Polynomial Regression (degree 2)
- Random Forest Regressor
- Artificial Neural Network (MLP)
- XGBoost Regressor
- Support Vector Regression (SVR)
- Gradient Boosting Regressor

Evaluation Metrics:
-------------------
- MAE (Mean Absolute Error)
- RMSE (Root Mean Squared Error)
- R² (Coefficient of Determination)
- High-purity slice analysis (xD ≥ 0.95)

How to Run:
-----------
1. Open `main.ipynb` in Jupyter Notebook or JupyterLab
2. Run all cells sequentially
3. The notebook will:
   - Load the dataset
   - Split data into Train/Validation/Test
   - Scale features and outputs
   - Train all six models
   - Evaluate and compare metrics
   - Generate diagnostics plots (parity, residual, sensitivity)
4. Results will be printed and plots will be displayed inline.

Notes:
------
- Python version: >=3.8
- Required libraries: pandas, numpy, scikit-learn, xgboost, matplotlib, seaborn, reportlab
- Install requirements with: pip install -r requirements.txt (create one if needed)

Contact:
--------
For questions or clarifications, please reach out to the project owner.

