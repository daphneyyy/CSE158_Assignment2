# Predictive Analysis on Clothing Fit using RentTheRunway Dataset

- This project aims to analyze the [_RentTheRunway_](https://cseweb.ucsd.edu/~jmcauley/datasets.html#clothing_fit) dataset and develop a predictive model for determining clothing fit based on various user-related measurements, reviews, and other relevant features.

- During the exploratory analysis of the dataset, several unexpected findings were observed. For instance, the distribution of sizes in the `large` class exhibited a right-skewed pattern, contrary to initial expectations. Users in this class tended to purchase smaller sizes compared to the other two classes (`small` and `fit`), which had less right-skewed and approximately normal distributions. Additionally, it was noticed that the distributions of `weight` and `height` displayed similar shapes and spreads.

- Four different classifiers, namely Logistic Regression, Decision Tree, SGD, and LinearSVC, were evaluated for the predictive task of determining clothing fit. Among these models, the Decision Tree classifier emerged as the top performer based on the weighted F1 scores obtained during validation and testing.

- To further enhance the performance of the model, additional features extracted from user comments were considered. The Bag of Words technique was employed to tokenize and preprocess the text from `review_text` and `review_summary` columns. The most frequent 4000 words were selected as the bag-of-words representation for these features.

- The final model incorporated the baseline features (baseline feature representation: `[1, d['weight'], d['height'], d['size']]`) along with the tokenized bag-of-words representation of the text features. This model yielded improved performance compared to the baseline model, with higher weighted F1 scores achieved during validation and testing.

- To address class imbalance in the dataset, undersampling was applied. This technique involved randomly sampling the `fit` class to create a balanced dataset, with an equal number of instances for each class. The resulting balanced dataset was then used for training, testing, and validation purposes.

- While the models showed improvements in predicting clothing fit, further optimization is still necessary to enhance their performance. One key parameter, `max_depth`, was tuned for the Decision Tree classifier to find the optimal value that maximized the weighted F1 score.

- Overall, this analysis provides valuable insights into predicting clothing fit using the RentTheRunway dataset. The findings highlight the significance of user measurements, reviews, and text features in accurately determining clothing fit and can guide further model refinement and optimization.
