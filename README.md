# 🍷 Wine Quality Prediction

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-Random%20Forest-orange)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-purple?logo=pandas)
![Scikit Learn](https://img.shields.io/badge/Scikit--Learn-ML-F7931E?logo=scikit-learn)
![Status](https://img.shields.io/badge/Project-Completed-success)

## 📌 About The Project

This project uses **Machine Learning to predict wine quality** based on its physicochemical properties.

The dataset is analyzed using **Exploratory Data Analysis (EDA)**, statistical analysis, data visualization, and correlation analysis. A **Random Forest Classifier** is then trained to classify wine into **Good Quality** or **Bad Quality**.

---

## 🎯 Project Objective

The main objectives of this project are:

* Analyze the Red Wine Quality dataset
* Understand the relationship between chemical properties and wine quality
* Perform data visualization and correlation analysis
* Prepare data for Machine Learning
* Train a classification model
* Evaluate model performance
* Build a system for predicting wine quality from new data

---

## 🧰 Technologies Used

| Technology       | Purpose                   |
| ---------------- | ------------------------- |
| 🐍 Python        | Programming               |
| 📊 Pandas        | Data manipulation         |
| 🔢 NumPy         | Numerical operations      |
| 📈 Matplotlib    | Data visualization        |
| 📊 Seaborn       | Statistical visualization |
| 🤖 Scikit-learn  | Machine Learning          |
| 🌲 Random Forest | Classification Model      |

---

## 📂 Dataset

The project uses the **Red Wine Quality Dataset**.

The dataset contains different physicochemical properties of wine along with a `quality` variable.

The dataset is loaded using:

```python
df = pd.read_csv("winequality-red.csv")
```

The project also checks the dataset dimensions and missing values before performing analysis.

---

## 🔎 Exploratory Data Analysis

The following analysis is performed:

### 📊 Statistical Analysis

The `describe()` function is used to understand the statistical characteristics of the dataset.

### 🍷 Quality Distribution

The number of wines belonging to each quality level is visualized using a count plot.

### 📈 Feature Analysis

The relationship between wine quality and:

* Volatile Acidity
* Citric Acid

is visualized using bar plots.

---

## 🔗 Correlation Analysis

A correlation matrix is created to identify relationships between the different numerical features.

A heatmap is used to visualize the correlations.

```python
correlation = df.corr()

sns.heatmap(
    correlation,
    cbar=True,
    square=True,
    fmt=".1f",
    annot=True,
    annot_kws={"size": 8},
    cmap="Blues"
)
```

---

## ⚙️ Data Preprocessing

The `quality` column is separated from the input features.

```python
X = df.drop("quality", axis=1)
Y = df["quality"]
```

The original quality values are converted into a binary classification:

```text
Quality >= 7  →  Good Quality (1)
Quality < 7   →  Bad Quality (0)
```

This transformation is implemented using label binarization.

---

## ✂️ Train-Test Split

The dataset is divided into training and testing datasets.

* **80% → Training Data**
* **20% → Testing Data**
* `random_state = 3`

```python
X_train, X_test, Y_train, Y_test = train_test_split(
    X,
    Y,
    test_size=0.2,
    random_state=3
)
```

---

## 🤖 Machine Learning Model

### Random Forest Classifier

The project uses the **Random Forest Classifier** for predicting wine quality.

```python
model = RandomForestClassifier()

model.fit(X_train, Y_train)
```

The trained model is then used to make predictions on the test dataset.

---

## 📊 Model Evaluation

The model is evaluated using **Accuracy Score**.

```python
X_test_prediction = model.predict(X_test)

test_data_accuracy = accuracy_score(
    X_test_prediction,
    Y_test
)

print("Accuracy : ", test_data_accuracy)
```

The project also imports tools for:

* Accuracy Score
* Confusion Matrix
* Classification Report

---

## 🔮 Prediction System

After training the model, a new wine sample can be provided to the system.

The input is converted into a NumPy array and reshaped before being passed to the trained model.

The final prediction is displayed as:

```text
Good Quality Wine
```

or

```text
Bad Quality Wine
```

---

## 📁 Project Structure

```text
Wine-Quality-Prediction/
│
├── wine_quality_prediction.py
├── winequality-red.csv
├── README.md
└── requirements.txt
```

---

## 🚀 Installation & Setup

### 1. Clone the Repository

```bash
git clone YOUR_REPOSITORY_URL
```

### 2. Open the Project Folder

```bash
cd Wine-Quality-Prediction
```

### 3. Install Dependencies

```bash
pip install numpy pandas matplotlib seaborn scikit-learn
```

### 4. Run the Project

```bash
python wine_quality_prediction.py
```

---

## 📋 Requirements

Create a `requirements.txt` file containing:

```text
numpy
pandas
matplotlib
seaborn
scikit-learn
```

---

## 💡 Key Learning Outcomes

Through this project, I gained practical experience in:

* Python for Data Science
* Data Cleaning
* Exploratory Data Analysis
* Data Visualization
* Correlation Analysis
* Data Preprocessing
* Classification
* Random Forest
* Model Training
* Model Evaluation
* Predictive Modeling

---

## 🔮 Future Improvements

* Compare Random Forest with other classification algorithms
* Perform hyperparameter tuning
* Add feature importance visualization
* Improve model evaluation with additional metrics
* Build an interactive **Streamlit** application
* Deploy the prediction model

---

## 👨‍💻 Author

### Ashish Kumar

**Aspiring Data Analyst | Data Scientist | AI/ML Enthusiast**

### Areas of Interest

`Data Analytics` • `Data Science` • `Machine Learning` • `Artificial Intelligence` • `Python`

---

## ⭐ If You Like This Project

If you found this project useful or interesting, please consider giving the repository a **⭐ Star**.

**Thank you for visiting!** 🚀
