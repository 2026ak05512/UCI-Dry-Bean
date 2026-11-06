Dry Bean Classification — BITS ML Assignment
Status: Project source and deployment-ready app are prepared. Run python train.py to fetch the official UCI data and generate the five fitted model files, held-out test_data.csv, and measured evaluation results. Do not submit placeholder metrics as experimental results.

a. Problem statement
The objective is to classify a dry bean sample into one of seven varieties using 16 numeric measurements extracted from bean images. Five supervised classification algorithms are trained and compared using the same stratified train/test split. The comparison uses Accuracy, macro one-vs-rest AUC, macro Precision, macro Recall, macro F1, and Matthews Correlation Coefficient (MCC).
b. Dataset description
- Dataset: UCI Dry Bean
- Source: UCI Machine Learning Repository — Dry Bean
- DOI: 10.24432/C50S4B
- Instances: 13,611
- Input features: 16 numeric features
- Target: Class
- Classes: Seker, Barbunya, Bombay, Cali, Dermosan, Horoz, Sira
- Missing values: UCI dataset description reports no missing values.
- License: Creative Commons Attribution 4.0 International (CC BY 4.0)
The 16 measurements describe area, perimeter, axis lengths, aspect ratio, eccentricity, convex area, equivalent diameter, extent, solidity, roundness, compactness and four shape factors.
c. GitHub Repository Link
Repository: ADD_YOUR_GITHUB_REPOSITORY_URL_HERE

The repository should include the complete Python source, requirements.txt, this README, test_data.csv, five fitted model files under models/, and generated evaluation artifacts under artifacts/.
d. Models used and evaluation metrics
Experimental setup
- One stratified 80% training / 20% test split.
- Fixed random seed: 42.
- The five models use the exact same split.
- Missing numeric values are handled by median imputation in each saved pipeline.
- Standardization is applied to Logistic Regression, KNN, Gaussian Naive Bayes and SVM.
- Decision Tree uses median imputation without feature scaling.
- AUC is macro one-vs-rest multiclass ROC AUC, calculated from predicted class probabilities.
- Precision, Recall and F1 are macro averages so each class contributes equally.
- The uploaded test CSV is evaluated using saved models. The Streamlit app does not retrain.
Model comparison table
Run python train.py; the script replaces this placeholder with measured held-out test results.
<!-- METRICS_TABLE -->Observations on model performance
The script generates metric-based observations after training.
ML Model Name	Observation about model performance


<!-- OBSERVATIONS_TABLE -->Overall winner for this dataset (highest macro F1): <!-- WINNER -->

Do not assume one algorithm is the winner before running the experiment. The winner is determined from the actual held-out test scores.
Streamlit application
Live app: ADD_YOUR_STREAMLIT_COMMUNITY_CLOUD_URL_HERE

The app supports:
1. Upload a labelled CSV containing the 16 features and Class.
2. Select one of the five saved classifiers.
3. Display Accuracy, AUC, Precision, Recall, F1 and MCC.
4. Display a confusion matrix and classification report.
5. Compare all five saved models on the uploaded test CSV.
6. Download predictions.
