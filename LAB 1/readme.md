# Find-S Algorithm using Two Datasets

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge\&logo=python)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Find--S-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Dataset](https://img.shields.io/badge/Datasets-2-success?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=for-the-badge)

---

# Find-S Algorithm

This project demonstrates the implementation of the Find-S Algorithm in Machine Learning using two different datasets:

1. Enjoy Sport Dataset
2. Play Tennis Dataset

The Find-S algorithm is a concept learning algorithm that determines the most specific hypothesis that fits all positive training examples.

---

# Project Structure

```text
LAB 1/
│
├── enjoy_sport.csv
├── play_tennis.csv
├── find_s_enjoy_sport.py
├── find_s_play_tennis.py
├── find_s.ipynb
├── Find_S_Report.pdf
└── README.md
```

---

# Aim

To implement the Find-S Algorithm and determine the most specific hypothesis from the given positive training examples.

---

# Objectives

* To understand the working of the Find-S Algorithm.
* To identify positive and negative examples from a dataset.
* To generate the final hypothesis based on positive examples.
* To compare the output of Find-S on two different datasets.

---

# Algorithm Used

## Find-S Algorithm Steps

1. Initialize the hypothesis with the first positive example.
2. Consider only positive training examples.
3. For every attribute:

   * If the attribute value is the same, keep it.
   * If the attribute value is different, replace it with `?`.
4. Continue until all positive examples are processed.
5. The remaining hypothesis is the final hypothesis.

---

# Dataset 1: Enjoy Sport Dataset

## Dataset Description

The Enjoy Sport dataset contains information about weather conditions and whether a sport can be enjoyed.

### Attributes

* Sky
* AirTemp
* Humidity
* Wind
* Water
* Forecast

### Sample Dataset

```text
Sky,AirTemp,Humidity,Wind,Water,Forecast,EnjoySport
Sunny,Warm,Normal,Strong,Warm,Same,Yes
Sunny,Warm,High,Strong,Warm,Same,Yes
Rainy,Cold,High,Strong,Warm,Change,No
Sunny,Warm,High,Strong,Cool,Change,Yes
```

## Expected Final Hypothesis

```text
['Sunny', 'Warm', '?', 'Strong', '?', '?']
```

---

# Dataset 2: Play Tennis Dataset

## Dataset Description

The Play Tennis dataset contains weather conditions and determines whether tennis can be played.

### Attributes

* Outlook
* Temperature
* Humidity
* Windy

### Sample Dataset

```text
Outlook,Temperature,Humidity,Windy,Play
Sunny,Hot,High,False,No
Sunny,Hot,High,True,No
Overcast,Hot,High,False,Yes
Rainy,Mild,High,False,Yes
Rainy,Cool,Normal,False,Yes
```

## Expected Final Hypothesis

```text
['?', '?', '?', '?']
```

---

# Source Code

## Read Dataset

```python
import pandas as pd

# Read dataset
Data = pd.read_csv("play_tennis.csv")
print(Data)
```

## Find-S Algorithm

```python
import pandas as pd

# Load dataset
Data = pd.read_csv("play_tennis.csv")

# Separate concepts and target
concepts = Data.iloc[:, :-1].values
target = Data.iloc[:, -1].values

# Find first positive example
for i in range(len(target)):
    if target[i].lower() == 'yes':
        hypothesis = concepts[i].copy()
        break

# Apply Find-S
for i in range(len(concepts)):
    if target[i].lower() == 'yes':
        for j in range(len(hypothesis)):
            if hypothesis[j] != concepts[i][j]:
                hypothesis[j] = '?'

print("Final Hypothesis:", hypothesis)
```

---

# How to Run

## Step 1: Install Python

Make sure Python is installed on your system.

```bash
python --version
```

## Step 2: Install Required Library

```bash
pip install pandas
```

## Step 3: Open Terminal in LAB 1 Folder

```bash
cd "LAB 1"
```

## Step 4: Run the Program

For Enjoy Sport Dataset:

```bash
python find_s_enjoy_sport.py
```

For Play Tennis Dataset:

```bash
python find_s_play_tennis.py
```

---

# Output

## Enjoy Sport Dataset Output

```text
Initial Hypothesis: ['Sunny', 'Warm', 'Normal', 'Strong', 'Warm', 'Same']
Final Hypothesis: ['Sunny', 'Warm', '?', 'Strong', '?', '?']
```

## Play Tennis Dataset Output

```text
Initial Hypothesis: ['Overcast', 'Hot', 'High', 'False']
Final Hypothesis: ['?', '?', '?', '?']
```

---

# Observations

* The algorithm ignores all negative examples.
* Only positive examples are used to generalize the hypothesis.
* If all positive examples differ in an attribute, the attribute becomes `?`.
* The Play Tennis dataset results in a completely generalized hypothesis.
* The Enjoy Sport dataset gives a more specific hypothesis.

---

# Advantages

* Simple and easy to understand.
* Useful for learning concept formation.
* Works well with small datasets.
* Helps understand supervised learning.

---

# Limitations

* Considers only positive examples.
* Cannot handle noisy data effectively.
* Produces only one most specific hypothesis.
* Not suitable for complex real-world datasets.

---

# Expected Outcome

After completing this experiment, the user will:

* Understand how the Find-S Algorithm works.
* Learn how to train a hypothesis using positive examples.
* Be able to apply Find-S to different datasets.
* Compare hypotheses generated from multiple datasets.

---

# Applications

* Weather prediction
* Basic concept learning
* Educational Machine Learning experiments
* Training beginner ML models

---

# Author

**Geethanjali M**
B.E Student | Machine Learning Enthusiast

---

# GitHub Repository Tips

Inside your repository, keep the folder structure like:

```text
Repository/
└── LAB 1/
    ├── enjoy_sport.csv
    ├── play_tennis.csv
    ├── find_s_enjoy_sport.py
    ├── find_s_play_tennis.py
    ├── find_s.ipynb
    ├── Find_S_Report.pdf
    └── README.md
```

This makes your project look clean and professional.
