aimlmid2026_n_chorgoliani25

AI and ML for Cybersecurity – Midterm Exam
Nika Chorgoliani
January 9, 2026

Task 1 – Finding Pearson Correlation
Data Collection

The data points were collected manually by hovering over the points on the provided online graph.
The coordinates were confirmed visually and saved into a CSV file for further processing.

Methodology

Pearson's correlation coefficient was calculated using the scipy.stats.pearsonr function in Python.
This method measures the strength and direction of a linear relationship between two continuous variables.

Results

The calculated Pearson correlation coefficient is:

r = 0.9977

p-value ≈ 1.19 × 10⁻¹⁰

This result indicates a very strong positive linear correlation between the variables, and the extremely low p-value confirms that the correlation is statistically significant.
Visualization

The scatter plot below shows the relationship between X and Y values, along with a fitted linear trend line.

Task 2 – Spam Email Classification using Logistic Regression
Dataset

The dataset contains 2500 email records with the following features:

words – total number of words in the email

links – number of URLs present

capital_words – number of fully capitalized words

spam_word_count – count of spam-related keywords

The target variable is is_spam (1 = spam, 0 = legitimate).

Dataset file:
emails.csv (uploaded in this repository)
Methodology

A Logistic Regression classifier was used to distinguish between spam and legitimate emails.

Steps performed:

The dataset was loaded using pandas.

Features and target labels were separated.

The data was split into training (80%) and testing (20%) sets.

A Logistic Regression model with max_iter = 1000 was trained using scikit-learn.

Model performance was evaluated on unseen test data.

Source code:
Python code used for this task is provided in this repository (Colab notebook / Python script).

Model Coefficients

The learned coefficients of the Logistic Regression model show that:

spam_word_count and capital_words have the strongest positive impact on predicting spam.

links also contributes positively to spam detection.

words has a smaller influence compared to other features.

This confirms that the model relies on meaningful spam-related indicators.

Model Evaluation Results

Accuracy: 94.6%

Confusion Matrix:

True Negatives (Legitimate correctly classified): 229

False Positives (Legitimate classified as spam): 4

False Negatives (Spam classified as legitimate): 23

True Positives (Spam correctly classified): 244

Classification Performance:

Precision (Spam): 0.98

Recall (Spam): 0.91

F1-score (Spam): 0.95

These results demonstrate strong overall performance with high precision and recall for spam detection.
Manual Spam Email Test (#5)

Composed Spam Email:

URGENT WINNER! You have been selected to claim your FREE CASH prize now.
Click https://bit.ly/offer
 to get your bonus. Limited time offer, buy now!
CONGRATULATIONS! Claim your money now.

Result:
The trained Logistic Regression model classified this email as spam (class = 1) with a spam probability of 0.9997.

Explanation:
This email was intentionally composed using multiple spam indicators such as urgent language, repeated spam-related keywords, capitalized words, and an external link. These features significantly increase the likelihood of spam classification by the model.

Manual Legitimate Email Test (#6)

Composed Legitimate Email:

Hi team,
Please find the meeting notes attached. Let me know if you have any questions.
Thanks,
Nika

Result:
The model classified this email as legitimate (class = 0) with a very low spam probability.

Explanation:
This email does not contain spam-related keywords, external links, or excessive capitalization, resulting in low spam feature values and correct classification as legitimate.

Visualizations (#7)

Visualization 1 – Class Distribution
A bar chart was created to visualize the distribution of spam versus legitimate emails in the dataset.
This visualization shows that the dataset is relatively balanced, which helps prevent bias during model training.

Visualization 2 – Confusion Matrix Heatmap
A heatmap representation of the confusion matrix was generated using matplotlib.
The visualization highlights that the model correctly classifies most emails, with very few false positives and false negatives.

Conclusion

This project demonstrates the application of machine learning techniques in cybersecurity through spam email detection. Logistic Regression proved to be an effective and interpretable model, achieving high accuracy and strong classification performance. Such models can serve as a foundational component in real-world email filtering and cybersecurity defense systems.
