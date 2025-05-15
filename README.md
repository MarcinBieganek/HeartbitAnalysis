# HeartbitAnalysis


### Project Objective

The objective of this project was to analyze medical data from Heartbit dataset and build a predictive model for classifying the severity of heart failure according to the NYHA (New York Heart Association) classification. The models aimed to automatically assign patients to one of four NYHA categories, which can support diagnosis and monitoring of patients with cardiovascular diseases.

### Data and Preparation

The data originated from a CSV file containing measurements and clinical information of patients. Key steps in data preparation included:

NYHA Value Transformation: The original dataset contained NYHA values of 1, 1.5, 2, 2.5, 3, 3.5, and 4. To simplify the model, these categories were merged into four groups:

    1 and 1.5 → 1

    2 and 2.5 → 2

    3 and 3.5 → 3

    4 → 4

Categorical Encoding: All text-type features were numerically encoded using LabelEncoder to allow for further analysis and modeling.

Handling Missing Data: Features with more than 50% missing values were removed. Remaining missing values were imputed using the KNN Imputer method (k=5), preserving as much information as possible.

Correlation Reduction: Features with very high correlation (above 0.9) were removed to prevent redundancy and improve model stability.

Data Standardization: Numerical features were standardized to have a mean of zero and a standard deviation of one, a common practice for many machine learning algorithms.

### Modeling

The dataset was split into training and testing sets in an 80:20 ratio. Two classification models were then trained:

* **Logistic Regression**: A linear model suitable for multi-class classification with interpretable coefficients.
* **Random Forest**: An ensemble model that handles non-linearities and feature interactions more effectively.

### Results

The logistic regression model achieved approximately 67% accuracy on the test set, performing well for classes 1 and 2, but showing difficulties classifying class 4 due to very few samples. The results were summarized using a classification report (precision, recall, f1-score).
