# 📩 SMS Spam Detection using Machine Learning

## 📌 Project Overview

SMS Spam Detection is a Natural Language Processing (NLP) and Machine Learning project that classifies SMS messages into two categories:

- **Ham:** Legitimate messages
- **Spam:** Unwanted or promotional messages

The project explores text preprocessing, exploratory data analysis, feature extraction, and multiple machine learning classification algorithms to identify spam messages.

## 🎯 Objectives

- Clean and preprocess SMS message data.
- Explore differences between spam and legitimate messages.
- Extract meaningful text features using TF-IDF.
- Train and compare multiple machine learning classifiers.
- Evaluate model performance using accuracy, precision, and confusion matrices.
- Experiment with ensemble learning techniques.

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming and analysis |
| Pandas, NumPy | Data manipulation and numerical operations |
| NLTK | Text preprocessing and tokenization |
| Scikit-learn | Feature extraction, model training, and evaluation |
| Matplotlib, Seaborn | Data visualization |
| WordCloud | Visualizing frequently occurring words |
| Jupyter Notebook | Development and experimentation |
| Pickle | Saving the trained model and TF-IDF vectorizer |

## 📂 Project Structure

```text
SMS-Spam-Detection/
│
├── SMS_Spam_Detection.ipynb
├── spam.csv
├── model.pkl
├── vectorizer.pkl
└── README.md
```

- `SMS_Spam_Detection.ipynb` — Data analysis, text preprocessing, model training, and evaluation.
- `spam.csv` — SMS message dataset.
- `model.pkl` — Serialized machine learning model.
- `vectorizer.pkl` — Serialized TF-IDF vectorizer.
- `README.md` — Project documentation.

## 📊 Dataset

The dataset contains SMS messages labeled as spam or ham.

**Initial dataset dimensions:** 5,572 rows and 5 columns.

The notebook removes three unnecessary columns, renames the relevant columns to `target` and `text`, encodes the target labels, and removes duplicate messages.

After cleaning and deduplication, the dataset is used for exploratory analysis and model development.

## 🔍 Project Workflow

### 1. Data Cleaning and Preparation

- Loaded the dataset using Pandas.
- Removed unnecessary columns.
- Renamed columns for clarity.
- Encoded the target labels.
- Checked for missing values and duplicate records.
- Removed duplicate messages.

### 2. Exploratory Data Analysis (EDA)

Explored the dataset to understand message characteristics and differences between spam and ham messages.

Key analysis areas:

- Distribution of spam and ham messages.
- Number of characters, words, and sentences per message.
- Message-length distributions by class.
- Relationships between numerical features.
- Common words in spam and legitimate messages.
- Word clouds for spam and ham messages.

**Visualizations:** Pie charts, histograms, pair plots, correlation heatmaps, word clouds, and bar charts.

### 3. Text Preprocessing

Created a text transformation function to prepare messages for machine learning.

The process includes:

1. Converting text to lowercase.
2. Tokenizing messages.
3. Removing non-alphanumeric tokens.
4. Removing English stop words and punctuation.
5. Applying Porter stemming.
6. Joining the processed tokens into transformed text.

### 4. Feature Extraction

Used **TF-IDF (Term Frequency–Inverse Document Frequency)** to convert the processed text into numerical features.

The notebook uses:

- `TfidfVectorizer`
- Maximum of 3,000 features
- An 80/20 training and testing split
- A fixed random state of 2

### 5. Model Training

Experimented with several classification algorithms:

- Gaussian Naive Bayes
- Multinomial Naive Bayes
- Bernoulli Naive Bayes
- Support Vector Classifier (SVC)
- K-Nearest Neighbors
- Logistic Regression
- Decision Tree
- Random Forest
- AdaBoost
- Bagging Classifier
- Extra Trees Classifier
- Gradient Boosting
- XGBoost

Also experimented with **Voting Classifier** and **Stacking Classifier** ensemble methods.

### 6. Model Evaluation

Evaluated classifiers using:

- **Accuracy:** Overall proportion of correct predictions.
- **Precision:** Proportion of predicted spam messages that were actually spam.
- **Confusion Matrix:** Breakdown of correct and incorrect classifications.

The notebook compares model performance to explore the trade-offs between different classification approaches.

## 📈 Results

The notebook reports the following results for the initial model comparisons:

| Algorithm | Accuracy | Precision |
|---|---:|---:|
| Support Vector Classifier | 97.58% | 97.48% |
| Multinomial Naive Bayes | 97.10% | 100.00% |
| Random Forest | 97.39% | 98.26% |
| Extra Trees Classifier | 97.49% | 97.46% |
| Logistic Regression | 95.55% | 96.00% |
| XGBoost | 97.00% | 95.73% |

These values are from the notebook's 80/20 train-test experiment. Results may vary with changes to preprocessing, feature extraction, data splitting, or model configuration.

**Evaluation note:** The current notebook fits TF-IDF on the complete dataset before splitting it into training and testing sets. This can introduce data leakage. For a more reliable evaluation, split the raw data first and fit the vectorizer only on the training messages. Re-run the experiment before treating these scores as final performance estimates.

## 💾 Saved Model Artifacts

The repository includes two serialized files:

- `model.pkl` — Saved Multinomial Naive Bayes classifier.
- `vectorizer.pkl` — Saved TF-IDF vectorizer.

These artifacts can be loaded with Python's `pickle` module for further experimentation. The vectorizer and model must be used with the same preprocessing pipeline and compatible feature representation.

**Security note:** Only load pickle files from sources you trust.

## 🚀 Getting Started

### Prerequisites

Install Python and the required libraries.

### 1. Clone the repository

```bash
git clone <your-github-repository-url>
cd SMS-Spam-Detection
```

### 2. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn nltk wordcloud xgboost jupyter
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open `SMS_Spam_Detection.ipynb` and execute the cells in order. The notebook downloads the required NLTK resources during execution.

Ensure `spam.csv` is in the expected working directory.

## 💡 Key Learnings

- Data cleaning and preparation for text classification.
- Exploratory analysis of imbalanced text datasets.
- NLP preprocessing with NLTK.
- TF-IDF feature extraction.
- Training and comparing multiple classification algorithms.
- Evaluating models with accuracy, precision, and confusion matrices.
- Exploring voting and stacking ensemble techniques.
- Saving machine learning artifacts for reuse.

## 🔮 Future Improvements

- Prevent data leakage by fitting TF-IDF only on training data.
- Use stratified train-test splitting and cross-validation.
- Tune model hyperparameters.
- Evaluate recall, F1-score, and precision-recall trade-offs.
- Test on new, unseen SMS messages.
- Build a simple web interface or API for spam prediction.

## 👨‍💻 Author

**Hrithik Raj**

- LinkedIn: https://linkedin.com/in/hrithik-raj-92085b291
- GitHub: https://github.com/Hrithik08raj

---

⭐ If you find this project useful, consider giving the repository a star.

