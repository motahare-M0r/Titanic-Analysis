# 🚢 Titanic Survival Analysis

Exploratory Data Analysis (EDA) of Titanic passenger data using **Python** with **Pandas**, **NumPy**, **Matplotlib**, and **Seaborn**.

---

## 📋 Table of Contents
- [About The Project](#-about-the-project)
- [Prerequisites & Installation](#-prerequisites--installation)
- [Project Structure](#-project-structure)
- [Dataset](#-dataset)
- [Visualizations](#-visualizations)
- [Key Findings](#-key-findings)
- [How to Run](#-how-to-run)
- [Libraries Used](#-libraries-used)
- [Resources](#-resources)

---

## 📖 About The Project

This project performs Exploratory Data Analysis (EDA) on the famous **Titanic** dataset. The main goal is to analyze factors that influenced passenger survival rates using statistical visualizations and data mining techniques.

**Key Questions:**
1. What percentage of passengers survived?
2. How does gender affect survival chances?
3. What impact did passenger class have on survival?

---

## ⚙️ Prerequisites & Installation

### Install Python
Make sure Python 3.7 or higher is installed on your system:
```bash
python --version
```

### Install Required Libraries

**Method 1 - Install all at once using requirements.txt:**
```bash
pip install -r requirements.txt
```

**Method 2 - Install each library separately:**
```bash
# Install Pandas and NumPy
pip install pandas numpy

# Install Matplotlib
pip install matplotlib

# Install Seaborn
pip install seaborn

# Install Jupyter Notebook (optional)
pip install jupyter
```

> 💡 **Recommendation**: Use a Virtual Environment:
> ```bash
> python -m venv titanic_env
> # On Windows:
> titanic_env\Scripts\activate
> # On Mac/Linux:
> source titanic_env/bin/activate
> ```

### requirements.txt file
```txt
pandas>=1.5.0
numpy>=1.23.0
matplotlib>=3.6.0
seaborn>=0.12.0
jupyter>=1.0.0
```

---

## 📁 Project Structure

```
titanic-analysis/
│
├── Titanic.ipynb          # Main Jupyter Notebook file
├── titanic.csv            # Titanic dataset
├── ti.jpg                 # Titanic image for header
├── README.md              # Project documentation
├── requirements.txt       # Required libraries list
└── output/                # Output charts folder (optional)
    ├── survival_by_gender.png
    └── survival_by_class.png
```

---

## 📊 Dataset

### Dataset Specifications
- **Total Records**: 891 passengers
- **Total Features**: 16 columns
- **Source**: [Kaggle Titanic Dataset](https://www.kaggle.com/c/titanic)

### Main Columns
| Column | Description | Values |
|--------|-------------|--------|
| `survived` | Survival status | 0 = Dead, 1 = Survived |
| `pclass` | Passenger class | 1 = First, 2 = Second, 3 = Third |
| `sex` | Gender | male / female |
| `age` | Age | 0.42 to 80 years |
| `fare` | Ticket price | 0 to 512 |
| `embarked` | Port of embarkation | S, C, Q |

### Missing Values
- **Age**: 177 missing values (filled with age >= 42)
- **Deck**: 688 missing values
- **Embarked**: 2 missing values

---

## 📈 Visualizations

### 1. Average Survival by Gender
```python
sns.barplot(data=titanic, x="sex", y="survived", palette=["blue", "pink"])
```
- **Result**: Females had significantly higher average survival rates than males.

### 2. Count of Living and Dead by Gender
```python
sns.countplot(data=titanic, x="survived", hue="sex")
```
- **Result**: 
  - Dead males: 468
  - Survived females: 233
  - Survived males: 109
  - Dead females: 81

### 3. Advanced Visualization (Class + Gender + Survival)
```python
g = sns.catplot(
    data=titanic,
    x="pclass",
    hue="sex",
    col="survived",
    kind="count",
    palette={"female": "#FF6B6B", "male": "#4ECDC4"}
)
```

---

## 🎯 Key Findings

### Overall Survival Statistics
- **Overall Survival Rate**: 38.4%
- **Survived Females**: 233 (74.2% of all females)
- **Survived Males**: 109 (18.9% of all males)

### Survival Rate by Class
| Class | Female Survival Rate | Male Survival Rate |
|-------|---------------------|-------------------|
| First | 96.8% | 36.9% |
| Second | 92.1% | 15.7% |
| Third | 50.0% | 13.7% |

### Conclusions
1. **Gender** was the most significant survival factor (women had priority)
2. **Passenger class** directly impacted survival chances
3. The "Women and children first" rule is clearly visible in this data

---

## 🚀 How to Run

### Run with Jupyter Notebook (Recommended)
```bash
# Start Jupyter
jupyter notebook

# Open Titanic.ipynb file
# Run cells sequentially (Shift + Enter)
```

### Run with VS Code
1. Open VS Code
2. Open `Titanic.ipynb` file
3. Click "Run All" or run cells one by one

### Run as Python Script
```bash
# Convert Notebook to Python script
jupyter nbconvert --to script Titanic.ipynb

# Run the script
python Titanic.py
```

---

## 📚 Libraries Used

### 1. **NumPy** - Numerical Computing
```python
import numpy as np
```
- Mathematical operations on arrays
- Statistical functions

### 2. **Pandas** - Data Management
```python
import pandas as pd
```
- Read/write CSV files
- Data manipulation (groupby, pivot, merge)
- Handle missing values

### 3. **Matplotlib** - Basic Plotting
```python
import matplotlib.pyplot as plt
```
- Basic charts (bar, line, scatter)
- Detailed chart customization

### 4. **Seaborn** - Advanced Visualization
```python
import seaborn as sns
```
- Beautiful statistical visualizations
- Attractive color palettes
- Seamless integration with Pandas

---

## 🔗 Resources

- [Titanic Dataset on Kaggle](https://www.kaggle.com/c/titanic)
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Seaborn Documentation](https://seaborn.pydata.org/)
- [Matplotlib Documentation](https://matplotlib.org/stable/contents.html)

---

## 📝 Common Issues & Solutions

**Error: ModuleNotFoundError**
```bash
pip install library_name
```

**Error: FileNotFoundError**
- Make sure `titanic.csv` is in the same folder as the Notebook file

**Error: MemoryError**
- Check your data with `titanic.head()`

---

## 👥 Contributing

If you have ideas to improve this analysis:
1. Fork the repository
2. Create a new branch
3. Apply your changes
4. Submit a Pull Request

---

## 📄 License

This project is licensed under the **MIT** License.

---

## ✍️ Author

Motahare Mortezaiee - motahareh.mortezaieegmail.com - https://github.com/motahare-M0r

---

**⭐ Don't forget to star this project if you found it helpful!**

---

### Complete requirements.txt file:
```txt
pandas==1.5.3
numpy==1.24.3
matplotlib==3.7.1
seaborn==0.12.2
jupyter==1.0.0
notebook==6.5.4
```
