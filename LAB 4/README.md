
# 🧠 Artificial Neural Network (ANN) - Backpropagation

![Python](https://img.shields.io/badge/Python-3.x-blue)
![NumPy](https://img.shields.io/badge/NumPy-Used-orange)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Used-yellow)
![Status](https://img.shields.io/badge/Project-Completed-brightgreen)

---

## 📌 Project Overview

This project implements a **simple Artificial Neural Network (ANN)** using the **Backpropagation algorithm**.
The model is trained on the **Iris dataset** to classify flowers into three categories.

---

## 🎯 Objectives

* Understand the working of ANN
* Implement Forward Propagation
* Implement Backpropagation
* Train and evaluate the model
* Achieve high classification accuracy

---

## 🧾 Dataset

* **Dataset Name:** Iris Dataset
* **Features:**

  * Sepal Length
  * Sepal Width
  * Petal Length
  * Petal Width
* **Target Classes:**

  * Setosa
  * Versicolor
  * Virginica

---

## ⚙️ Technologies Used

* Python
* NumPy
* Pandas
* Scikit-learn

---

## 🏗️ Model Architecture

```
Input Layer:    4 Neurons
Hidden Layer:   8 Neurons
Output Layer:   3 Neurons
```

---

## 🔁 Working Process

### 1. Data Loading

* Load Iris dataset

### 2. Preprocessing

* Normalize data using StandardScaler
* Convert labels using one-hot encoding

### 3. Training

* Forward Propagation
* Calculate Loss
* Backpropagation (update weights)

### 4. Testing

* Predict on test data
* Calculate accuracy

---

## ▶️ How to Run

```bash
# Install dependencies
pip install numpy pandas scikit-learn

# Run the program
python ann.py
```

---

## 📊 Sample Output

```
============================================================
ARTIFICIAL NEURAL NETWORK - BACKPROPAGATION
============================================================
1. Loading Iris dataset...
Dataset shape: (150, 4)

2. Preprocessing data...
Training samples: 120
Test samples: 30

3. Creating Neural Network...
Architecture: 4 -> 8 -> 3

4. Training Neural Network...
Epoch 0, Loss: 1.0986
Epoch 100, Loss: 0.4523
Epoch 200, Loss: 0.2876
Epoch 300, Loss: 0.2154
Epoch 400, Loss: 0.1765

5. Evaluating on test set...
Test Accuracy: 96.67%

============================================================
Final Test Accuracy: 96.67%
============================================================
```

---

## 📈 Results

* Achieved **~96% accuracy**
* Model successfully classifies iris flowers

---

## 🧠 Key Concepts

* Artificial Neural Network (ANN)
* Forward Propagation
* Backpropagation
* Activation Functions (Sigmoid, Softmax)
* Loss Function (Cross-Entropy)

---

## 🚀 Future Improvements

* Add more hidden layers (Deep Learning)
* Use different activation functions (ReLU)
* Hyperparameter tuning
* Visualization of decision boundaries

---

## 👩‍💻 Author

**Geethanjali M**

---

## ⭐ Conclusion

This project demonstrates how a simple ANN with backpropagation can effectively solve classification problems with good accuracy.

---
