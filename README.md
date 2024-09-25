# **Crosswalk Usage Preference Analysis**

Project Overview

This repository contains Python code to analyze crosswalk usage preferences based on a survey dataset. The analysis focuses on demographic variables and responses to Likert-scale questions regarding crosswalk safety and usability. Several machine learning models are used to predict respondents' preferences, with a particular focus on those who respond with 'No' to crosswalk usage.
Table of Contents
1. Project Overview
2. Dataset Information
3. Analysis Steps
4. Machine Learning Models
5. Feature Importance
6. How to Use
7. Dependencies
8. Results
Dataset Information
The dataset used contains the following variables:

- **Demographic Variables**:
  - `D1`: Gender
  - `D2`: Age
  - `D3`: Crosswalk Usage Frequency

- **Preference**: The target variable with responses labeled as 'Yes' or 'No'.
  - Encoded as:
    - `0` for 'Yes' (crosswalk usage)
    - `1` for 'No' (crosswalk avoidance)

- **Likert-Scale Variables**: The independent variables related to perceptions of crosswalk safety and usability.
  - `V1`: Crosswalk usage is time-consuming
  - `V2`: Absence of guard rails on median
  - `V3`: Unsuitability of crosswalk location
  - `V4`: Feel unsafe to cross directly without crosswalk
  - `V5`: Inadequate marking and sign to locate crosswalk
  - `V6`: Poor entry access to crosswalk
  - `V7`: Difficulty crossing roads using crosswalk
  - `V8`: Inadequate lighting at night near crosswalk

Analysis Steps
1. **Label Encoding**: 
   - The Likert-scale variables are encoded as a 5-point scale (1-5).
   - The `Preference` variable is encoded as `0` for 'Yes' and `1` for 'No', with 'No' being the primary focus of the analysis.

2. **Descriptive Statistics**: 
   - The dataset is summarized using counts, percentages, and statistics like mean and standard deviation for Likert-scale variables.

3. **Correlation Analysis**: 
   - Spearman correlation is calculated and plotted for Likert-scale variables to examine the relationships between different factors.

4. **Machine Learning Models**: 
   - Three machine learning models are used for binary classification:
     - CART (Decision Tree)
     - Random Forest
     - XGBoost
   - The dataset is split into training and testing sets using stratified sampling to ensure a balanced representation of classes.
   - Evaluation metrics are computed, including Accuracy, F1-Score, Sensitivity, Specificity, MCC (Matthews Correlation Coefficient), and AUROC.

5. **Confusion Matrix**: 
   - Confusion matrices are generated for both training and testing data to assess model performance.

6. **Feature Importance**: 
   - Feature importance is plotted for the best-performing model based on MCC. The importance of each feature (such as perceptions of crosswalk usability) is visualized to show their influence on the model's decision-making process.
Machine Learning Models
The models used include:

- **CART** (Classification and Regression Tree)
- **Random Forest**: An ensemble model using multiple decision trees.
- **XGBoost**: A high-performance boosting algorithm.

Each model is evaluated using the following metrics:

- F1 Score
- Accuracy
- Sensitivity (Recall)
- Precision
- Specificity
- False Positive Rate (FPR)
- True Negative Rate (TNR)
- Matthews Correlation Coefficient (MCC)
- Area Under the ROC Curve (AUROC)

Feature Importance
The feature importance for the best-performing model (based on MCC) is plotted to show which factors most influence the prediction of a 'No' response. For example, if `V3: Unsuitability of crosswalk location` is the most important feature, this suggests that people who perceive crosswalk locations as unsuitable are more likely to avoid using them.
How to Use
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/crosswalk-usage-analysis.git
   ```

2. Install the necessary dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Place your dataset in the project folder.

4. Run the analysis:
   ```bash
   python analysis.py
   ```
Dependencies
The project requires the following Python libraries:

- pandas
- numpy
- scikit-learn
- seaborn
- matplotlib
- xgboost

You can install all dependencies using:
```bash
pip install -r requirements.txt
```
Results
- **Confusion Matrices**: Display the performance of each model on training and testing data.
- **Evaluation Metrics**: A table of F1 Score, Accuracy, Sensitivity, Precision, Specificity, FPR, TNR, MCC, and AUROC for each model.
- **Feature Importance**: A horizontal bar chart showing the most influential variables, sorted by their impact on the model's predictions.
License

This project is licensed under the MIT License.
