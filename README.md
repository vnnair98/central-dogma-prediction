# central-dogma-prediction

This project was completed as part of a class project during my master’s at the University of Pennsylvania.

Over the last decade, one of the most transformative breakthroughs in biology has been the advent of single-cell sequencing. For this project, I focused on using single-cell RNA expression data to predict the levels of corresponding cell-surface proteins in human bone marrow stem cells (HSCs) as they differentiate into mature blood cells. This touches directly on the central dogma of molecular biology—DNA makes RNA, which makes protein—and explores how predictive modeling can be used to bridge two layers of this process.

The dataset consisted of readings from approximately 300,000 cells collected across five developmental time points. I trained three different models—Linear Regression, Random Forest, and a Feed Forward Neural Network—using data from the first four time points and evaluated their performance on the unseen fifth time point to test generalization to future stages of cell differentiation.

This kind of modeling has the potential to augment biological research by enabling researchers to infer protein-level information directly from transcriptomic data, saving time, cost, and experimental complexity.

## Summary of Findings
Given the computational intensity of a multi-output regression problem, I selected the top 1,000 most variable genes as features, along with cell type information. Surprisingly, simple linear regression outperformed other models, achieving a Pearson correlation coefficient just under 0.90 across 140 protein targets—indicating strong predictive power using a relatively straightforward model.

I also explored non-linear models such as Random Forest and the HistGradientBoostingRegressor. While these models offered slight improvements, the gains were marginal and limited by training time and lack of hyperparameter tuning. Interestingly, attempts at regularization tended to reduce performance, suggesting that a more complex feature set or modeling approach may be needed to improve accuracy.

## Future Work
Scale up feature selection to include the top 5,000 genes to capture non-linear trends

Perform dimensionality reduction (e.g., PCA) in a distributed environment

Use GridSearchCV for more thorough hyperparameter tuning

Explore deep learning models to better model complex gene-protein relationships

Investigate variance explained by more than 10,000 principal components (sklearn limitation)

## Technologies Used
- Python (NumPy, Pandas, Scikit-learn, PyTorch)

- Jupyter Notebooks

- Matplotlib/Seaborn for visualization

## Models Trained
Linear Regression

Random Forest Regressor

Feed Forward Neural Network

## Dataset
Single-cell RNA and protein expression data (~300,000 cells) from human bone marrow stem cells across 5 developmental time points. Source: Kaggle
