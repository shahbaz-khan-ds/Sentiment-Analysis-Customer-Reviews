# Sentiment Analysis on Customer Reviews using NLP

## Project Overview

This project focuses on analyzing customer reviews using Natural Language Processing (NLP) and Machine Learning techniques.

The objective is to classify customer reviews into three sentiment categories:

- Positive
- Neutral
- Negative

The project uses the Women's E-Commerce Clothing Reviews dataset and compares three machine learning classification algorithms.

## Dataset

**Dataset:** Women's E-Commerce Clothing Reviews

The dataset contains customer reviews and product-related information.

After data cleaning:

- Total reviews processed: 22,641
- Target variable: Rating-derived sentiment
- Sentiment classes: Positive, Neutral, Negative

### Sentiment Labeling

Sentiment categories were created using customer ratings:

| Rating | Sentiment |
|---|---|
| 1–2 | Negative |
| 3 | Neutral |
| 4–5 | Positive |

Note: These are rating-derived labels, so they represent review-rating categories rather than independently human-annotated text sentiment.

## Technologies Used

- Python
- Jupyter Notebook
- Pandas
- NumPy
- NLTK
- Scikit-learn
- Matplotlib
- Seaborn
- TF-IDF

## Project Workflow

### 1. Data Cleaning
- Removed unnecessary index column.
- Handled missing values.
- Removed records with missing review text.
- Prepared categorical columns.

### 2. Exploratory Data Analysis (EDA)
- Analyzed rating distribution.
- Examined sentiment distribution.
- Visualized review length.
- Analyzed frequent words.
- Examined sentiment across product departments.

### 3. Text Preprocessing
- Lowercase conversion.
- HTML tag removal.
- URL and unwanted character removal.
- Tokenization.
- Stopword removal while preserving negation terms.
- Lemmatization.

### 4. Feature Extraction

Used TF-IDF (Term Frequency–Inverse Document Frequency) to convert textual reviews into numerical features.

Configuration:
- Maximum features: 10,000
- N-gram range: (1, 2)
- Minimum document frequency: 2
- Maximum document frequency: 0.95

### 5. Model Building

Three machine learning models were trained:

1. Logistic Regression
2. Multinomial Naive Bayes
3. Linear Support Vector Machine (Linear SVM)

### 6. Model Evaluation

Models were evaluated using:

- Accuracy
- Precision
- Recall
- Macro F1-score
- Confusion Matrix

## Model Performance

Results from the saved notebook:

| Model | Test Accuracy | Macro F1-score |
|---|---:|---:|
| Logistic Regression | 78.43% | 0.61 |
| Multinomial Naive Bayes | 78.60% | 0.39 |
| Linear SVM | **80.83%** | **0.61** |

**Best accuracy:** Linear SVM — 80.83%.

The displayed Macro F1-scores are rounded to two decimal places. Therefore, they should not be used to distinguish very small differences between models.

### Key Observations

- Linear SVM achieved the highest test accuracy.
- Logistic Regression showed competitive performance.
- Multinomial Naive Bayes struggled to identify minority sentiment classes.
- Positive reviews were easier to classify than Neutral and Negative reviews.

## Dataset Limitations

The sentiment labels were generated from star ratings. A customer's written review may not always express the same sentiment as their rating.

The dataset also has class imbalance, with Positive reviews making up approximately 77% of the cleaned dataset.

For this reason, accuracy alone is not sufficient to evaluate model performance.

## Project Structure

```text
Sentiment-Analysis-Customer-Reviews/
│
├── Sentiment_analyses.ipynb
├── README.md
├── requirements.txt
│
└── images/
    ├── sentiment_distribution.png
    ├── rating_distribution.png
    ├── word_frequency.png
    └── model_comparison.png
```

Add only the image files that you actually export from your notebook.

## Installation and Usage

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### 2. Navigate to the project directory

```bash
cd Sentiment-Analysis-Customer-Reviews
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Open Jupyter Notebook

```bash
jupyter notebook
```

Open `Sentiment_analyses.ipynb` and execute the cells.

The dataset must be downloaded separately and placed in the location expected by the notebook, if your notebook uses a local CSV file.

## Future Improvements

- Hyperparameter tuning using cross-validation.
- Improve minority-class prediction.
- Compare review text against title-plus-review text.
- Experiment with contextual language models such as DistilBERT.
- Evaluate using an independently human-annotated sentiment dataset.

## Conclusion

This project demonstrates an end-to-end NLP workflow for customer review classification, including data cleaning, exploratory analysis, text preprocessing, TF-IDF feature extraction, machine learning model development, and performance evaluation.

Linear SVM achieved the highest test accuracy of 80.83% among the three evaluated models.

## Author

Your Name

GitHub: YOUR_GITHUB_PROFILE_URL