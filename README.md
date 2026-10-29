# Machine Learning and Explainable AI for Fraud Detection

This repository contains the reproducible analysis developed for the RPDA8412 Research Project. The study compares five supervised machine-learning classifiers on the public Kaggle Credit Card Fraud Detection dataset and evaluates the selected Random Forest model with SHAP and LIME.

## Research focus

The analysis addresses three questions:

1. How do Logistic Regression, Decision Tree, Random Forest, linear Support Vector Machine and k-Nearest Neighbours compare on an extremely imbalanced fraud dataset?
2. Which features drive the strongest model's predictions according to SHAP and LIME, and how consistent are the explanations?
3. What do the results imply for fraud analytics and POPIA-informed model governance in South African financial institutions?

## Repository contents

- `notebooks/RPDA8412_Fraud_Detection_XAI.ipynb` - end-to-end research notebook.
- `outputs/` - saved model metrics, confusion matrices, XAI summaries and report figures.
- `report/ST10295312_RPDA8412_Final_Research_Report_Rubric_Aligned.docx` - final research report.
- `requirements.txt` - Python package requirements.

## Dataset

The raw transaction dataset is not stored in this repository because of its size. Download the **Credit Card Fraud Detection** dataset from Kaggle and save the CSV as `data/creditcard.csv` before running the notebook:

https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

The dataset contains 284,807 anonymised European card transactions from September 2013, including 492 fraudulent transactions. It is used as a methodological benchmark and is not presented as evidence of current South African fraud prevalence.

## Reproducing the analysis

1. Create a Python virtual environment.
2. Install the dependencies with `pip install -r requirements.txt`.
3. Place the Kaggle CSV at `data/creditcard.csv`.
4. Open and run `notebooks/RPDA8412_Fraud_Detection_XAI.ipynb` from top to bottom.

The workflow uses a stratified 80:20 split with random seed 42. Scaling and resampling are fitted to training data only, while the test set retains its natural class imbalance.

## Principal result

Random Forest achieved the strongest combined F1-score and PR-AUC under the common test conditions. SHAP and LIME agreed most strongly for the selected confidently classified cases and less strongly for selected errors. The findings support an XAI-first evaluation framework, but not direct deployment: responsible use requires recent local data, operational validation, human review and ongoing governance.

## Academic context

This repository accompanies an academic research report submitted for RPDA8412. The scripts and notebook support reproducibility and inspection of the reported results. The report remains the authoritative account of the methodology, limitations and conclusions.

