# Phishing-website-detection-
this project is about the today phising link scams occurs in the large no this detection system specifies that wether a website is legitimate or phishng website 

# Phishing Website Detection System

A machine learning web application that checks a website and tells you whether it is **phishing** or **legitimate**, to help protect users from online fraud.

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Flask](https://img.shields.io/badge/Backend-Flask-lightgrey)
![scikit-learn](https://img.shields.io/badge/ML-scikit--learn-orange)
![Status](https://img.shields.io/badge/Type-Academic%20Project-informational)

---

## Table of Contents

- [About the Project](#about-the-project)
- [Problem Statement](#problem-statement)
- [Objectives](#objectives)
- [Features](#features)
- [How It Works](#how-it-works)
- [Tech Stack](#tech-stack)
- [Dataset](#dataset)
- [Machine Learning Models](#machine-learning-models)
- [Results](#results)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Screenshots](#screenshots)
- [Future Scope](#future-scope)
- [Authors](#authors)
- [Disclaimer](#disclaimer)
- [References](#references)

---

## About the Project

A phishing website is a fake website made to look like a real one, such as a bank login page or an online shopping site. Its goal is to trick people into entering their username, password, or card details.

Most protection today relies on **blacklists**, which only block a site after someone has already reported it. By then, the attacker has often moved on to a new fake website.

This project takes a different approach. Instead of waiting for a report, it uses **machine learning** to learn the text patterns that phishing websites usually share, and then predicts whether a new website is phishing or legitimate. The trained model is served through a simple web page built with Flask, so anyone can use it without any technical knowledge.

## Problem Statement

> Develop a machine learning system that detects and classifies websites as phishing or legitimate, to help protect users from online fraud.

## Objectives

1. Build a machine learning model that can tell whether a website is phishing or legitimate.
2. Clean and convert website text into a format the model can learn from.
3. Train and compare two models: Logistic Regression and Multinomial Naive Bayes.
4. Reduce the need for manually updated blacklists by making detection automatic.
5. Make the model easy to use through a simple web page built with Flask and HTML/CSS.

## Features

- Simple web form to enter a website or URL
- Automatic text cleaning, tokenization, and stemming
- Text-to-number conversion using CountVectorizer
- Instant result: **Phishing** or **Legitimate**
- Trained model saved with Pickle, so it does not need to be retrained on every request
- Data exploration with charts and a word cloud

## How It Works

```
Raw website / URL text
        |
        v
Cleaning (Regex)
        |
        v
Tokenization
        |
        v
Stemming (Snowball Stemmer)
        |
        v
Vectorization (CountVectorizer)
        |
        v
Classifier (Logistic Regression / Multinomial Naive Bayes)
        |
        v
Prediction: Phishing or Legitimate
```

1. **Data collection:** a labelled "good / bad" website dataset from Kaggle.
2. **Preprocessing:** NumPy, Pandas, Regex, Tokenization, Snowball Stemmer, and CountVectorizer.
3. **Exploratory analysis:** Matplotlib, Seaborn, and WordCloud.
4. **Model training:** Logistic Regression and Multinomial Naive Bayes.
5. **Model saving:** the trained model is stored with Pickle.
6. **Deployment:** a Flask backend with an HTML/CSS frontend.

## Tech Stack

| Category | Technology / Tool |
|---|---|
| Frontend | HTML, CSS |
| Backend | Python (Flask) |
| Machine Learning | scikit-learn (Logistic Regression, Multinomial Naive Bayes) |
| Text Processing | Regex, Tokenization, NLTK Snowball Stemmer, CountVectorizer |
| Data Handling | NumPy, Pandas |
| Visualization | Matplotlib, Seaborn, WordCloud |
| Model Saving | Pickle |
| Development Tool | VS Code |
| Operating System | Windows / Linux |

## Dataset

- **Source:** Kaggle, "good / bad" website dataset
- **Classes:** `good` (legitimate) and `bad` (phishing)
- **Format:** each record has the website/URL text and its label
- The data is split into training and test sets to check how well the model works on unseen websites.

> Add the exact Kaggle dataset link here: `[Dataset link]`

## Machine Learning Models

| Model | Why it is used |
|---|---|
| **Logistic Regression** | A simple, fast linear classifier that works well as a strong baseline for text features. |
| **Multinomial Naive Bayes** | A probabilistic classifier designed for word-count data, and it handles the large, sparse feature matrix from CountVectorizer well. |

Both models are trained on the same CountVectorizer features and compared using accuracy, precision, recall, and F1-score.

## Results

Fill in the table below with the scores from your own experiments.

| Model | Accuracy | Precision | Recall | F1-score |
|---|---|---|---|---|
| Logistic Regression | - | - | - | - |
| Multinomial Naive Bayes | - | - | - | - |

## Project Structure

> This is a suggested layout. Update it to match the files in your repository.

```
phishing-website-detection/
|-- app.py                  # Flask backend
|-- templates/
|   |-- index.html          # Frontend page
|-- static/
|   |-- style.css           # Styling
|-- model/
|   |-- model.pkl           # Trained classifier (Pickle)
|   |-- vectorizer.pkl      # Fitted CountVectorizer (Pickle)
|-- notebook/
|   |-- training.ipynb      # Data cleaning, EDA, and model training
|-- data/
|   |-- dataset.csv         # Kaggle dataset (or download link)
|-- requirements.txt
|-- README.md
```

## Getting Started

### Prerequisites

- Python 3.x
- pip
- Git

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/[your-username]/[your-repo-name].git
cd [your-repo-name]

# 2. (Recommended) Create a virtual environment
python -m venv venv

# Windows
venv\Scripts\activate
# macOS / Linux
source venv/bin/activate

# 3. Install the required libraries
pip install -r requirements.txt
```

If your repository does not have a `requirements.txt` yet, create one with these packages:

```
numpy
pandas
scikit-learn
nltk
matplotlib
seaborn
wordcloud
flask
```

### Run the App

```bash
python app.py
```

Then open **http://127.0.0.1:5000** in your browser.

### How to Use

1. Open the web page.
2. Enter the website or URL you want to check.
3. Click the check/submit button.
4. The page shows whether the website looks **Phishing** or **Legitimate**.

### Retraining the Model (optional)

Run the training notebook or script to clean the data, retrain both models, and regenerate the saved Pickle files. Then restart the Flask app so it loads the new model.

## Screenshots

Add screenshots of your app here, for example:

```
![Home page](screenshots/home.png)
![Phishing result](screenshots/phishing_result.png)
![Legitimate result](screenshots/legitimate_result.png)
```

## Future Scope

- Mobile app version of the detector
- Browser extension that checks websites automatically while browsing
- Deep learning models (such as LSTM or BERT) for better accuracy on tricky cases
- Integration with live threat-intelligence feeds
- Regularly growing the training dataset as new phishing patterns appear

## Authors
[Himanshu Bhardwaj]

## Disclaimer

This is an academic project built for learning purposes. No machine learning model is 100% accurate, so please do not rely on this tool alone to decide whether a website is safe. Always be careful before entering personal or payment details online.

## References

- [scikit-learn Documentation](https://scikit-learn.org/stable/documentation.html)
- [NLTK Documentation](https://www.nltk.org/)
- [Flask Documentation](https://flask.palletsprojects.com/)
- [NumPy Documentation](https://numpy.org/doc/)
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Kaggle](https://www.kaggle.com/)
