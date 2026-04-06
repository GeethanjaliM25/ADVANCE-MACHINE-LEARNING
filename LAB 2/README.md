# Candidate Elimination Algorithm using Two Datasets

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge\&logo=python)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Candidate%20Elimination-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen?style=for-the-badge)
![Datasets](https://img.shields.io/badge/Datasets-2-success?style=for-the-badge)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge\&logo=jupyter)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=for-the-badge)

---

# Candidate Elimination Algorithm

This project demonstrates the implementation of the Candidate Elimination Algorithm using two different datasets:

1. Enjoy Sport Dataset
2. Play Tennis Dataset

The Candidate Elimination Algorithm computes all possible hypotheses that are consistent with the training examples. It maintains two boundaries:

* Specific Boundary (S)
* General Boundary (G)

---

# Project Structure

```text
LAB 2/
│
├── enjoy_sport.csv
├── tennis.csv
├── candidate_elimination_enjoy_sport.py
├── candidate_elimination_play_tennis.py
├── candidate_elimination.ipynb
├── Candidate_Elimination_Report.pdf
└── README.md
```

---

# Aim

To implement the Candidate Elimination Algorithm on the Enjoy Sport and Play Tennis datasets in order to determine the specific and general boundaries of the version space.

---

# Objectives

* To understand the concept of version space in Machine Learning.
* To learn how the Candidate Elimination Algorithm updates both S and G boundaries.
* To distinguish between positive and negative examples.
* To implement the algorithm using two datasets.
* To compare the final hypotheses generated from different datasets.
* To understand how specialization and generalization are performed.

---

# Algorithm Used

## Candidate Elimination Steps

1. Initialize the Specific Boundary (S) with the first positive example.
2. Initialize the General Boundary (G) with the most general hypothesis.
3. For every positive example:

   * Generalize S if necessary.
   * Remove inconsistent hypotheses from G.
4. For every negative example:

   * Specialize G to exclude the negative example.
   * Remove inconsistent hypotheses from S.
5. Continue until all examples are processed.
6. The remaining S and G are the final version space boundaries.

---

# Dataset 1: Enjoy Sport Dataset

## Dataset Description

The Enjoy Sport dataset contains weather-related conditions and whether a sport can be enjoyed.

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

## Final Output for Enjoy Sport Dataset

```text
Specific Boundary (S):
['Sunny', 'Warm', '?', 'Strong', '?', '?']

General Boundary (G):
['Sunny', '?', '?', '?', '?', '?']
['?', 'Warm', '?', '?', '?', '?']
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

## Final Output for Play Tennis Dataset

```text
Specific Boundary (S):
['?', '?', '?', '?']

General Boundary (G):
[]
```

---

# Source Code

```python
import pandas as pd

# Read dataset
Data = pd.read_csv("play_tennis.csv")

# Separate concepts and target
concepts = Data.iloc[:, :-1].values.tolist()
target = Data.iloc[:, -1].values.tolist()

# Initialize Specific Hypothesis
for i in range(len(target)):
    if target[i].lower() == 'yes':
        S = concepts[i].copy()
        break

# Initialize General Hypothesis
G = [['?' for i in range(len(S))]]

# Candidate Elimination Algorithm
for i in range(len(concepts)):

    if target[i].lower() == 'yes':
        for j in range(len(S)):
            if S[j] != concepts[i][j]:
                S[j] = '?'

        G = [g for g in G if all(g[k] == '?' or g[k] == S[k] for k in range(len(S)))]

    else:
        new_G = []

        for j in range(len(S)):
            if S[j] != concepts[i][j] and S[j] != '?':
                temp = ['?' for k in range(len(S))]
                temp[j] = S[j]
                if temp not in new_G:
                    new_G.append(temp)

        if new_G:
            G = new_G

print("Specific Boundary:", S)
print("General Boundary:", G)
```

---

# How to Run

## Step 1: Install Required Library

```bash
pip install pandas
```

## Step 2: Open Terminal in LAB 2 Folder

```bash
cd "LAB 2"
```

## Step 3: Run the Program

For Enjoy Sport Dataset:

```bash
python candidate_elimination_enjoy_sport.py
```

For Play Tennis Dataset:

```bash
python candidate_elimination_play_tennis.py
```

---

# Observations

* The Candidate Elimination Algorithm maintains both a specific and a general hypothesis.
* Positive examples make the specific boundary more general.
* Negative examples make the general boundary more specific.
* The Enjoy Sport dataset results in a meaningful version space with both S and G boundaries.
* The Play Tennis dataset is highly diverse, so the specific boundary becomes fully generalized.
* For the Play Tennis dataset, the general boundary becomes empty because no consistent general hypothesis remains.
* The algorithm works best with small and noise-free datasets.

---

# Advantages

* Considers both positive and negative examples.
* Produces all consistent hypotheses.
* Helps understand version space learning.
* More informative than the Find-S Algorithm.

---

# Limitations

* Difficult to use with large datasets.
* Cannot handle noisy or contradictory data effectively.
* The version space may become empty if the dataset is highly inconsistent.
* More complex than the Find-S Algorithm.

---

# Expected Outcome

After successful completion of this experiment:

* The user will understand the Candidate Elimination Algorithm.
* The user will learn how S and G boundaries are updated.
* The user will be able to apply the algorithm to different datasets.
* The user will compare the behavior of the algorithm on Enjoy Sport and Play Tennis datasets.
* The user will understand why the Play Tennis dataset results in an empty general boundary.

---

# Applications

* Concept learning
* Weather-based prediction systems
* Educational Machine Learning experiments
* Understanding version space learning

---

# Author

**Geethanjali M**
B.E Student | Machine Learning Enthusiast

---

# GitHub Repository Structure

```text
Repository/
└── LAB 2/
    ├── enjoy_sport.csv
    ├── tennis.csv
    ├── candidate_elimination_enjoy_sport.py
    ├── candidate_elimination_play_tennis.py
    ├── candidate_elimination.ipynb
    ├── Candidate_Elimination_Report.pdf
    └── README.md
```

This structure keeps the project clean, professional, and easy to understand.

