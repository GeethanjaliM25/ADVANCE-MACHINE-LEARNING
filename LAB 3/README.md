
# ID3 Algorithm (Decision Tree) using Two Datasets

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge\&logo=python)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-ID3-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Datasets](https://img.shields.io/badge/Datasets-2-success?style=for-the-badge)
![Library](https://img.shields.io/badge/Library-scikit--learn-yellow?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=for-the-badge)

---

# ID3 Algorithm

This project demonstrates the implementation of the ID3 (Iterative Dichotomiser 3) Algorithm using two datasets:

1. Enjoy Sport Dataset
2. Play Tennis Dataset

ID3 is a decision tree algorithm that uses **Entropy** and **Information Gain** to select the best attribute for splitting the data.

---

# Project Structure

```text
LAB 3/
│
├── enjoy_sport.csv
├── tennis.csv
├── id3_enjoy_sport.py
├── id3_play_tennis.py
├── id3.ipynb
├── ID3_Report.pdf
└── README.md
```

---

# Aim

To implement the ID3 Algorithm on the Enjoy Sport and Play Tennis datasets and construct decision trees based on entropy and information gain.

---

# Objectives

* To understand the concept of decision trees in Machine Learning.
* To learn how entropy and information gain are calculated.
* To implement ID3 using Python.
* To analyze how attributes are selected as root and internal nodes.
* To compare decision trees generated from two different datasets.

---

# Algorithm Used

## ID3 Algorithm Steps

1. Calculate entropy of the dataset.
2. For each attribute, calculate information gain.
3. Select the attribute with highest information gain as root.
4. Split dataset based on selected attribute.
5. Repeat the process recursively for each subset.
6. Stop when all examples belong to same class or no attributes remain.

---

# Dataset 1: Enjoy Sport Dataset

## Description

This dataset contains weather conditions to decide whether a sport can be enjoyed.

### Attributes

* Sky
* AirTemp
* Humidity
* Wind
* Water
* Forecast

### Sample Data

```text
Sky,AirTemp,Humidity,Wind,Water,Forecast,EnjoySport
Sunny,Warm,Normal,Strong,Warm,Same,Yes
Sunny,Warm,High,Strong,Warm,Same,Yes
Rainy,Cold,High,Strong,Warm,Change,No
Sunny,Warm,High,Strong,Cool,Change,Yes
```

## Expected Behavior

* Decision tree is simple due to small dataset.
* Attributes like Sky and AirTemp dominate decision making.

---

# Dataset 2: Play Tennis Dataset

## Description

This dataset determines whether tennis can be played based on weather conditions.

### Attributes

* Outlook
* Temperature
* Humidity
* Windy

### Sample Data

```text
Outlook,Temperature,Humidity,Windy,Play
Sunny,Hot,High,False,No
Sunny,Hot,High,True,No
Overcast,Hot,High,False,Yes
Rainy,Mild,High,False,Yes
Rainy,Cool,Normal,False,Yes
```

## Expected Behavior

* Root node: Outlook
* Sunny → depends on Humidity
* Rainy → depends on Windy
* Overcast → always Yes

---

# Source Code (ID3 using sklearn)

```python
import pandas as pd
from sklearn.tree import DecisionTreeClassifier, export_text

# Load dataset
Data = pd.read_csv("play_tennis.csv")

# Convert categorical to numeric
for col in Data.columns:
    Data[col] = Data[col].astype('category').cat.codes

# Split features and target
X = Data.iloc[:, :-1]
y = Data.iloc[:, -1]

# Train model using entropy (ID3)
model = DecisionTreeClassifier(criterion='entropy')
model.fit(X, y)

# Print decision tree
print(export_text(model, feature_names=list(X.columns)))
```

---

# How to Run

## Step 1: Install Required Libraries

```bash
pip install pandas scikit-learn
```

## Step 2: Navigate to LAB 3 Folder

```bash
cd "LAB 3"
```

## Step 3: Run Programs

```bash
python id3_play_tennis.py
python id3_enjoy_sport.py
```

---

# Output

## Play Tennis Decision Tree (Simplified Rules)

```text
1. If Outlook = Overcast → Play = Yes
2. If Outlook = Sunny AND Humidity = High → Play = No
3. If Outlook = Sunny AND Humidity = Normal → Play = Yes
4. If Outlook = Rainy AND Windy = False → Play = Yes
5. If Outlook = Rainy AND Windy = True → Play = No
```

---

# Observations

* ID3 selects the attribute with highest information gain.
* Outlook is the root node in Play Tennis dataset.
* Decision trees become deeper when dataset is complex.
* Enjoy Sport dataset produces a simpler tree.
* Play Tennis dataset produces a more detailed tree.

---

# Advantages

* Easy to understand and interpret.
* Works well for categorical data.
* Builds tree using clear mathematical concept (entropy).

---

# Limitations

* Can overfit small datasets.
* Requires encoding of categorical data.
* Sensitive to noisy data.

---

# Expected Outcome

* Successful construction of decision trees for both datasets.
* Understanding of entropy and information gain.
* Ability to interpret decision tree rules.
* Comparison between simple and complex trees.

---

# Applications

* Weather prediction systems
* Decision-making systems
* Classification problems
* Educational Machine Learning experiments

---

# Author

**Geethanjali M**
B.E Student | Machine Learning Enthusiast

---

# GitHub Structure

```text
Repository/
└── LAB 3/
    ├── enjoy_sport.csv
    ├── tennis.csv
    ├── id3_enjoy_sport.py
    ├── id3_play_tennis.py
    ├── id3.ipynb
    ├── ID3_Report.pdf
    └── README.md
```

This structure ensures a clean and professional project organization.
