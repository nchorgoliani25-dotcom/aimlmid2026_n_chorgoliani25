# aimlmid2026_n_chorgoliani25
AI and ML for Cybersecurity – Midterm Exam  
Nika Chorgoliani  
January 9, 2026

---

## Task 1 – Finding Pearson Correlation

### Data Collection
The data points were collected manually by hovering over the points on the provided online graph.  
The coordinates were confirmed visually and saved into a CSV file for further processing.

### Methodology
Pearson's correlation coefficient was calculated using the `scipy.stats.pearsonr` function in Python.  
This method measures the strength and direction of a linear relationship between two continuous variables.

### Results
The calculated Pearson correlation coefficient is:
- **r = 0.9977**
- **p-value ≈ 1.19 × 10⁻¹⁰**

This result indicates a very strong positive linear correlation between the variables, and the extremely low p-value confirms that the correlation is statistically significant.

### Visualization
The scatter plot below shows the relationship between X and Y values, along with a fitted linear trend line.

![Correlation Plot](correlation_plot.png)

---

## Task 2 – Spam Email Classification using Logistic Regression

### Dataset
The dataset contains **2500 email records** with the following features:
- `words` – total number of words in the email  
- `links` – number of URLs present  
- `capital_words` – number of fully capitalized words  
- `spam_word_count` – count of spam-related keywords  

The target variable is `is_spam` (1 = spam, 0 = legitimate).

**Dataset file:**  
`emails.csv` (uploaded in this repository)

---

### Methodology
A **Logistic Regression** classifier was used to distinguish between spam and legitimate emails.

Steps performed:
1. The dataset was loaded using pandas.
2. Features and target labels were separated.
3. The data was split into **training (80%)** and **testing (20%)** sets.
4. A Logistic Regression model with `max_iter=1000` was trained using scikit-learn.
5. Model performance was evaluated on unseen test data.

**Source code:**  
Python code is provided in the repository (Colab notebook / Python script used during the exam).

---

### Model Coefficients
The learned coefficients of the Logistic Regression model show that:
- `spam_word_count` and `capital_words` have the strongest positive impact on predicting spam.
- `links` also contributes positively to spam detection.
- `words` has a smaller influence compared to other features.

This confirms that the model relies on meaningful spam-related indicators.

---

### Model Evaluation Results

- **Accuracy:** 94.6%

**Confusion Matrix:**
- True Negatives (Legitimate correctly classified): 229  
- False Positives (Legitimate classified as spam): 4  
- False Negatives (Spam classified as legitimate): 23  
- True Positives (Spam correctly classified): 244  

**Classification Performance:**
- Precision (Spam): 0.98  
- Recall (Spam): 0.91  
- F1-score (Spam): 0.95  

These results demonstrate strong overall performance with high precision and recall for spam detection.

---

### Manual Spam Email Test (#5)

**Composed Spam Email:**
