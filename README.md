# Duplicate Question Pairs Detection

A **Machine Learning-based web application** that identifies whether two questions are duplicates or not, inspired by the Quora question pairs problem. This project uses text preprocessing, feature engineering, and ML classification to predict duplicates.

---

## Table of Contents
- [Features](#features)
- [Technologies](#technologies)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [How it Works](#how-it-works)
- [Screenshots](#screenshots)
- [Contributing](#contributing)
- [License](#license)

---

## Features
- Detects duplicate questions using multiple **text-based features**:
  - Common words ratio
  - Token-based similarity
  - Length-based features
  - Fuzzy string matching features (Levenshtein distance-based)
  - Bag-of-words features
- Simple **Streamlit web interface** for user input.
- Generates predictions using a **pre-trained ML model**.

---

## Technologies
- **Python 3.11**
- **Scikit-learn** for ML modeling
- **FuzzyWuzzy** for string similarity
- **NLTK** for text preprocessing
- **Streamlit** for the web app
- **Pickle** for saving and loading models

---

## Installation

1. Clone the repository:
```bash
git clone https://github.com/Het-Patel-24/Duplicate-Question-Pairs.git
cd Duplicate-Question-Pairs
```

2. Create a virtual environment:
```bash
python3 -m venv .venv
source .venv/bin/activate  # Mac/Linux
.venv\Scripts\activate     # Windows
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Ensure the **model files** `model.pkl` and `cv.pkl` are in place for predictions.

---

## Usage
Run the Streamlit app:
```bash
streamlit run streamlit-app/app.py
```

- Enter **Question 1** and **Question 2** in the web form.
- Click **Find** to check if the questions are duplicates.

---

## Project Structure
```
Duplicate-Question-Pairs/
├─ streamlit-app/
│   ├─ app.py            # Streamlit frontend
│   ├─ helper.py         # Feature engineering and preprocessing
├─ model/
│   ├─ model.pkl         # Trained ML model
│   ├─ cv.pkl            # CountVectorizer for bag-of-words
├─ requirements.txt      # Python dependencies
├─ README.md             # Project documentation
```

---

## How it Works
1. **Preprocessing**:
   - Convert text to lowercase
   - Replace symbols and numbers with words
   - Remove stopwords

2. **Feature Extraction**:
   - Token features (common words, stops, first/last word matches)
   - Length-based features (question length, common substring length)
   - Fuzzy features using FuzzyWuzzy (`ratio`, `partial_ratio`, `token_sort_ratio`, `token_set_ratio`)
   - Bag-of-words representation using CountVectorizer

3. **Prediction**:
   - Features are fed into a **pre-trained ML classifier** (`RandomForest/XGBoost`)
   - Returns **Duplicate** or **Not Duplicate**

---

## Screenshots
![App Screenshot](link_to_screenshot.png)
- Input fields for Question 1 & Question 2
- Result displayed as **Duplicate** or **Not Duplicate**

---

## Contributing
1. Fork the repository
2. Create a branch (`git checkout -b feature-branch`)
3. Commit changes (`git commit -m 'Add new feature'`)
4. Push to branch (`git push origin feature-branch`)
5. Open a Pull Request

---

## License
This project is **MIT Licensed**. See `LICENSE` for details.

