
# 🌸 SVM IRIS — Binary Classification with Support Vector Machine

This project demonstrates a simple **binary classification task using a Support Vector Machine (SVM)** on a two-class subset of the well-known **Iris dataset**.

The main purpose of this project is to explore how a **Linear SVM** separates two classes and to examine the relative importance of the input features through the coefficients learned by the model.

---

## 📌 Project Overview

The dataset used in this project contains **100 samples** belonging to two classes of the Iris dataset.

Each sample contains four numerical features:

| Feature  | Description  |
| -------- | ------------ |
| `sl`     | Sepal Length |
| `sw`     | Sepal Width  |
| `pl`     | Petal Length |
| `pw`     | Petal Width  |
| `target` | Class label  |

The target variable contains two classes:

```text
0
1
```

Therefore, this project is a **binary classification problem**.

---

## 🔍 Feature Importance

A **Linear SVM** was used so that the coefficients of the learned decision boundary could also be examined.

The model produced approximately the following coefficients:

```python
[ 0.046, -0.521, 1.003, 0.464 ]
```

corresponding to:

```text
Sepal Length   →  0.046
Sepal Width    → -0.521
Petal Length   →  1.003
Petal Width    →  0.464
```

Looking at the absolute values of these coefficients, **Petal Length (`pl`) has the largest coefficient** and therefore has the strongest influence on the decision boundary in this trained linear SVM model.

This is the **third feature column** of the dataset.

> An important distinction is that `pl` represents **Petal Length (طول گلبرگ)**, while `sl` represents **Sepal Length (طول کاسبرگ)**.

The coefficient analysis can therefore be used as a simple feature-importance analysis for this linear model.

---

## 🧠 Model

The classifier used in this project is:

```python
SVC(kernel="linear")
```

A linear kernel was selected because it makes the separating hyperplane directly interpretable through the model coefficients.

---

## ✂️ Train-Test Split

The dataset was divided into training and testing sets using:

```python
train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

This produces:

```text
Training samples: 80
Testing samples:  20
```

Using `random_state=42` makes the train-test split reproducible, meaning that the same samples are selected each time the notebook is executed.

---

## 🎯 Model Performance

After training the SVM classifier, predictions were generated for the test dataset.

The resulting accuracy was:

```text
Accuracy = 1.00
```

or:

```text
100%
```

The confusion matrix was:

```text
[[12, 0],
 [ 0, 8]]
```

This means that all **20 test samples were classified correctly**.

There were:

* **12 correctly classified samples from Class 0**
* **8 correctly classified samples from Class 1**
* **0 misclassified samples**

---

## 📊 Why Did the Model Reach 100% Accuracy?

The Iris dataset is a very clean and well-structured dataset, and the two classes used in this experiment are highly separable based on their numerical features.

In particular, features such as **Petal Length** provide strong information for distinguishing between the two classes.

As a result, the Linear SVM was able to find a separating decision boundary that correctly classified every sample in this particular test split.

However, an accuracy of `1.00` should not automatically be interpreted as proof that a model will always achieve perfect performance on unseen data.

In this experiment:

* the dataset is relatively small,
* the data are clean,
* only two Iris classes are considered,
* the selected classes are relatively easy to separate,
* and the test set contains only 20 observations.

Therefore, the perfect result should be interpreted in the context of this specific experiment.

---

## 📦 Libraries Used

The project uses the following Python libraries:

```python
pandas
numpy
matplotlib
seaborn
scikit-learn
```

The main Scikit-learn components are:

```python
from sklearn.svm import SVC
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score, confusion_matrix
```

---

## 🔄 Project Workflow

```text
Iris Two-Class Dataset
        ↓
Data Loading
        ↓
Feature / Target Separation
        ↓
Train-Test Split
        ↓
Linear SVM
        ↓
Model Training
        ↓
Feature Coefficient Analysis
        ↓
Prediction
        ↓
Accuracy & Confusion Matrix
        ↓
Accuracy = 1.00
```

---

## 📈 Exploratory Analysis

A boxplot of the input features was also generated using Seaborn:

```python
sns.boxplot(data=X)
plt.show()
```

This provides a simple visual comparison of the distributions and ranges of the four Iris features.

---

## 💡 Key Takeaways

This small experiment demonstrates several fundamental Machine Learning concepts:

* Binary classification using **Support Vector Machines**
* Working with the **Iris dataset**
* Reproducible **train-test splitting**
* Using a **linear SVM**
* Interpreting linear SVM coefficients
* Basic **feature-importance analysis**
* Model prediction
* Accuracy evaluation
* Confusion matrix interpretation

A particularly interesting result was that **Petal Length (`pl`) had the largest coefficient in the trained Linear SVM**, suggesting that it played an important role in separating the two classes in this experiment.

The model achieved an accuracy of **1.00 (100%)** on the test set, with no misclassified observations.

---

## 📁 Repository

```text
SVM-IRIS/
│
├── SVM.ipynb
├── iris_2_class.csv
└── README.md
```

---

## 👩‍💻 Author

**Sara Javan Amoli**

Machine Learning Practice Project
Support Vector Machine — Iris Binary Classification
