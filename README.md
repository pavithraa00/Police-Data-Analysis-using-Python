# 🚓 Police Data Analysis Using Python

## 📌 Project Overview
This project performs exploratory data analysis (EDA) on a Police Traffic Stop dataset using Python and Pandas.  
The analysis focuses on violations, driver demographics, searches conducted during stops, and stop durations.

---

# 🛠️ Technologies Used
- Python
- Pandas
- Google Colab / Jupyter Notebook

---

# 📂 Dataset
The dataset contains information related to police traffic stops such as:
- Driver Gender
- Driver Age
- Violation Type
- Search Conducted
- Stop Duration

---

# 📊 Questions Solved in This Project

## 1️⃣ Remove Columns That Contain Only Null Values
Used Pandas functions to identify null values and remove unnecessary columns.

```python
data.isnull().sum()
data.drop(columns='country_name', inplace=True)
```

---

## 2️⃣ For Speeding, Were Men or Women Stopped More Often?
Filtered the dataset for speeding violations and counted gender occurrences.

```python
data[data['violation'] == 'Speeding']['driver_gender'].value_counts()
```

### ✅ Result
Men were stopped more often for speeding violations.

---

## 3️⃣ Does Gender Affect Who Gets Searched During a Stop?
Used `groupby()` to analyze searches conducted based on gender.

```python
data.groupby('driver_gender').search_conducted.sum()
```

---

## 4️⃣ What is the Mean Stop Duration?
Converted categorical stop durations into numerical values and calculated the mean.

```python
data['stp_duration'] = data['stop_duration'].map({
    '0-15 Min': 7.5,
    '16-30 Min': 24,
    '30+ Min': 45
})

data['stp_duration'].mean()
```

---

## 5️⃣ Compare the Age Distribution for Each Violation
Used descriptive statistics to compare driver age distributions.

```python
data.groupby('violation').driver_age.describe()
```

---


# 📈 Key Insights
- Male drivers were stopped more frequently for speeding.
- Search rates vary based on driver gender.
- Stop duration can be analyzed numerically after transformation.
- Different violations show different age distribution patterns.

---

# ▶️ How to Run the Project
1. Open the notebook in Google Colab or Jupyter Notebook.
2. Upload the dataset.
3. Run all cells step by step.

---

# 📁 Project Structure

```text
Police-Data-Analysis/
│
├── PoliceAnalysis.ipynb
├── Police Data.csv
├── README.md
└── images/
```

---

# 🌟 Future Improvements
- Add visualizations using Matplotlib and Seaborn
- Build an interactive dashboard
- Perform advanced statistical analysis

---

# 👩‍💻 Author
P. Pavithra Lakshmi
