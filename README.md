# News Category Classification

This project demonstrates a complete machine learning workflow for classifying news articles into four categories: Business, Sports, Crime, and Science. The model is built using Python, scikit-learn, and spaCy.

## Project Overview

The goal of this project is to automatically categorize news articles, a common task in Natural Language Processing (NLP). This repository contains a Jupyter Notebook that walks through the entire process, from data exploration and cleaning to model training and evaluation. The final model successfully classifies articles with **88% accuracy**.

## Dataset

The dataset consists of thousands of news headlines and short descriptions, each labeled with a category. The categories are:
- Business
- Sports
- Crime
- Science

## Methodology

The project follows these key steps:
1.  **Exploratory Data Analysis (EDA):** The initial dataset was found to be imbalanced, with significantly more articles in the 'Business' and 'Sports' categories.
2.  **Handling Class Imbalance:** To prevent model bias, the majority classes were **down-sampled** to create a balanced dataset.
3.  **Text Preprocessing:** The text data was cleaned using **spaCy** to remove stop words and punctuation, helping the model focus on meaningful words.
4.  **Modeling:** A `scikit-learn` pipeline was created using:
    - `CountVectorizer` to convert text into numerical feature vectors (using 1-grams and 2-grams).
    - `MultinomialNB` (Naive Bayes) classifier, a probabilistic algorithm well-suited for text data.
5.  **Evaluation:** The model's performance was measured using a classification report, achieving an overall accuracy of 88%.

## Results

Two models were compared: a baseline model trained on raw text and a second model trained on preprocessed text.

| Model                       | Accuracy | Key Improvement                                               |
| --------------------------- | :------: | ------------------------------------------------------------- |
| Baseline (Raw Text)         |   84%    | A strong starting point but weaker on the 'Business' category.|
| Final (Preprocessed Text)   |   88%    | Showed significant gains, especially in precision for 'Business'.|

Preprocessing the text to remove noise proved to be a critical step for improving model performance.

## Installation and Usage

To run this project on your local machine, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/news-category-classification.git](https://github.com/your-username/news-category-classification.git)
    cd news-category-classification
    ```

2.  **Create and activate a virtual environment (recommended):**
    ```bash
    # For Windows
    python -m venv venv
    .\venv\Scripts\activate

    # For macOS/Linux
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Download the spaCy language model:**
    ```bash
    python -m spacy download en_core_web_sm
    ```

5.  **Launch Jupyter Notebook and open the file:**
    ```bash
    jupyter notebook news_category_classification.ipynb
    ```

## Libraries Used
- pandas
- scikit-learn
- spaCy
- Jupyter
