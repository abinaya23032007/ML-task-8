Phishing Website Detection Using Linear SVM
Project Overview
This project uses a Linear Support Vector Machine (Linear SVM) to
classify website records as legitimate or phishing based on numerical
features from the PhiUSIIL Phishing URL Dataset. It evaluates the model
with classification metrics and visualizations.
Objectives
- Prepare the dataset for machine learning.
- Use numerical website features to train a Linear SVM classifier.
- Predict labels for unseen test data.
- Evaluate performance using a confusion matrix, precision, recall,
  F1-score, ROC-AUC, a classification report, and an ROC curve.
Technologies Used
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab or Jupyter Notebook
Dataset
The code expects a CSV file named PhiUSIIL_Phishing_URL_Dataset.csv.

The notebook reads the dataset from
/content/PhiUSIIL_Phishing_URL_Dataset.csv, which is a typical Google
Colab path. If you run the project locally, update the path to match the
location of your CSV file.
Workflow
1. Load the dataset using Pandas.
2. Inspect the data by checking its shape, columns, missing values,
   and class distribution.
3. Prepare the target and features by removing rows with missing
   labels and excluding label, URL, Domain, TLD, and Title
   from the input features.
4. Select numerical features and replace infinite values with
   missing values.
5. Handle missing feature values by filling them with the median.
6. Split the data into training and testing sets using an 80/20
   split and stratification.
7. Build the model pipeline using StandardScaler and LinearSVC,
   with balanced class weights.
8. Train and predict using the training set and test set.
9. Evaluate the model with a confusion matrix, precision, recall,
   F1-score, ROC-AUC, classification report, and ROC curve.
Installation
Install the required libraries:
pip install pandas numpy matplotlib seaborn scikit-learn
How to Run
1. Download or place PhiUSIIL_Phishing_URL_Dataset.csv in your
   environment.
2. Open Untitled11.ipynb in Google Colab or Jupyter Notebook, or run
   untitled11.py.
3. Update the dataset file path if necessary.
4. Run the cells or script in order.
5. Review the printed metrics and plots.
Evaluation Metrics
- Confusion Matrix: Summarizes correct and incorrect predictions
  for each class.
- Precision: Measures how many predictions for a class were
  correct.
- Recall: Measures how many actual cases of a class were
  identified.
- F1-score: Combines precision and recall into one score.
- ROC-AUC: Measures how well the model's decision scores
  distinguish the two classes.
- Classification Report: Shows precision, recall, F1-score, and
  support for each class.
- ROC Curve: Visualizes the trade-off between true positive rate
  and false positive rate.
Important Label-Mapping Note
The code creates the target with y = (df["label"] == 0).astype(int)
and displays encoded classes as Legitimate for 0 and Phishing for
1. This means original dataset label 0 is encoded as 1 in this
code. Verify the dataset's label definitions to ensure that the
class names used in the confusion matrix and classification report match
the actual labels. The README does not assume the dataset's original
label convention.
Current Limitations
- The notebook uses a fixed local/Colab dataset path that may need
  updating.
- The model uses numerical columns only; URL text fields listed in the
  code are excluded.
- The notebook reports evaluation metrics, but no actual metric values
  are included here because they depend on running the code against
  the dataset.
- The script reads and prepares the dataset more than once; this could
  be simplified.
Project Files
- untitled11.py --- Python script.
- Untitled11.ipynb --- Jupyter/Google Colab notebook.
- PhiUSIIL_Phishing_URL_Dataset.csv --- dataset required to run the
  project (not included in the uploaded files).
