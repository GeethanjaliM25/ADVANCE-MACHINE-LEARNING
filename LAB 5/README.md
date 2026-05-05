# 📊 Naive Bayesian Classifier (Iris Dataset)

![Python](https://img.shields.io/badge/Python-3.x-blue)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Used-yellow)
![Model](https://img.shields.io/badge/Model-Naive%20Bayes-green)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)

---

## 📌 Project Overview

This project implements a **Naive Bayesian Classifier** to classify flowers from the **Iris dataset**.
The model uses probability concepts based on **Bayes Theorem** to predict the class of a given sample.

---

## 🎯 Objectives

* Understand Naive Bayes algorithm
* Perform classification using probability
* Train and test the model on real dataset
* Evaluate performance using accuracy and classification report

---

## 🧾 Dataset

* **Dataset:** Iris Dataset
* **Source:** UCI Machine Learning Repository
* **Features:**

  * Sepal Length
  * Sepal Width
  * Petal Length
  * Petal Width
* **Classes:**

  * Iris-setosa
  * Iris-versicolor
  * Iris-virginica

---

## ⚙️ Technologies Used

* Python
* Pandas
* Scikit-learn

---

## 🔁 Working Process

### 1. Data Loading

* Load dataset from UCI repository

### 2. Data Splitting

* Split into training and testing sets

### 3. Model Training

* Train using **Gaussian Naive Bayes**

### 4. Prediction

* Predict class labels for test data

### 5. Evaluation

* Calculate accuracy
* Generate classification report

---

## ▶️ How to Run

```bash id="run1"
pip install pandas scikit-learn
python naive_bayes.py
```

---

## 📊 Sample Output

```id="out2"
==================================================
NAIVE BAYESIAN CLASSIFIER
==================================================
Test Accuracy: 95.56 %

Classification Report:

                 precision    recall  f1-score   support
Iris-setosa         1.00       1.00      1.00       15
Iris-versicolor     0.93       0.93      0.93       15
Iris-virginica      0.93       0.93      0.93       15
==================================================
```

---

## 📈 Results

* Achieved **~95% accuracy**
* Model performs well on all three classes

---

## 🧠 Key Concepts

* Naive Bayes Algorithm
* Bayes Theorem
* Gaussian Distribution
* Probability-based Classification

---

## 🚀 Future Improvements

* Try different datasets
* Improve accuracy with preprocessing
* Compare with other models (Decision Tree, ANN)

---

## 👩‍💻 Author

**Geethanjali M**

---

## ⭐ Conclusion

This project demonstrates how Naive Bayes can efficiently perform classification using simple probability concepts with high accuracy.

---

