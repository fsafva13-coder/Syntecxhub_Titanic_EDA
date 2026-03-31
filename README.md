# 🚢 Titanic Dataset EDA
> A full exploratory data analysis of the RMS Titanic passenger dataset — uncovering the factors that determined survival through statistical analysis and visualization.

![Python](https://img.shields.io/badge/Python-3.14-blue?style=flat&logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.x-darkblue?style=flat&logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-0.13-teal?style=flat&logo=python)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-orange?style=flat&logo=python)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?style=flat&logo=jupyter)
![Internship](https://img.shields.io/badge/Syntecxhub-Data%20Science%20Internship-purple?style=flat)

---

## 📌 Project Overview

On April 15, 1912, the RMS Titanic sank after striking an iceberg — killing 1,502 of 2,224 passengers and crew. The central question this EDA answers is: **what factors actually determined who survived?**

This project loads the Titanic dataset, inspects missingness and data types, analyzes survival rates across sex, passenger class and age groups, and visualizes the findings through bar charts, heatmaps, violin plots and boxplots. A 5-bullet insight report with actual survival statistics is exported at the end.

Built as part of the Syntecxhub Data Science Internship (Week 3, Project 1).

---

## ✨ Features

- **Full data inspection** — shape, dtypes, missing value count and percentage per column
- **Survival by sex** — survival rate comparison with stacked count chart
- **Survival by class** — bar chart + sex x class heatmap showing interaction effects
- **Age bucket analysis** — passengers grouped into Child, Teen, Young Adult, Middle Age and Senior
- **Age distribution overlay** — survived vs not survived histogram with mean lines
- **Split violin plot** — age distribution by sex and survival in one compact view
- **Fare boxplot** — fare distribution by class and survival, showing economic advantage
- **Multi-factor analysis** — sex x class grouped bar chart + embarkation port survival
- **5-bullet insight report** — exported to `titanic_insight_report.txt` with actual statistics

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.14 | Core programming language |
| Pandas | Data loading, cleaning and analysis |
| Seaborn | Statistical visualizations and built-in dataset |
| Matplotlib | Chart customization and export |
| NumPy | Numerical operations |
| Jupyter Notebook | Development and documentation environment |

---

## 📸 Charts

### Survival Rate by Sex
<img width="1924" height="722" alt="01_survival_by_sex" src="https://github.com/user-attachments/assets/4f1f1494-ba31-4dbf-ab5f-cce2ae9e03ee" />

### Survival by Passenger Class + Sex x Class Heatmap
<img width="1901" height="722" alt="02_survival_by_class" src="https://github.com/user-attachments/assets/0eceeef6-43e4-4b1f-b814-8f21c1a4ce62" />

### Survival by Age Group + Age Distribution
<img width="2074" height="722" alt="03_survival_by_age" src="https://github.com/user-attachments/assets/53c3c109-e69c-465a-9b99-bb7578ea5980" />

### Violin Plot (Age) + Boxplot (Fare)
<img width="2074" height="868" alt="04_violin_boxplot_age_fare" src="https://github.com/user-attachments/assets/3e0501a9-820c-438d-a101-02cb0aec78de" />

### Multi-Factor: Sex x Class + Embarkation Port
<img width="2074" height="722" alt="05_survival_multifactor" src="https://github.com/user-attachments/assets/6c049396-68ed-4d47-aa06-d954f1048b4e" />

---

## 🚀 Installation

1. Clone the repository
```bash
git clone https://github.com/fsafva13-coder/Syntecxhub_Titanic_EDA.git
cd Syntecxhub_Titanic_EDA
```

2. Install dependencies
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

3. Launch the notebook
```bash
jupyter notebook project1_titanic_eda.ipynb
```

4. Run all cells with **Kernel → Restart & Run All**

---

## 📋 Usage

The notebook loads the Titanic dataset directly from seaborn's built-in datasets — no external file needed.

**Pipeline flow:**
1. Dataset loaded and inspected — shape, dtypes, missing values
2. Survival rates computed by sex, class, age bucket and embarkation port
3. Charts generated and saved to `plots/` folder
4. 5-bullet insight report exported to `titanic_insight_report.txt`

---

## 📁 Project Structure

```
Syntecxhub_Titanic_EDA/
├── README.md
├── project1_titanic_eda.ipynb         ← main notebook
├── titanic_insight_report.txt         ← 5-bullet findings report
└── plots/
    ├── 01_survival_by_sex.png
    ├── 02_survival_by_class.png
    ├── 03_survival_by_age.png
    ├── 04_violin_boxplot_age_fare.png
    └── 05_survival_multifactor.png
```

---

## 📊 Key Findings

| Factor | Finding |
|---|---|
| Overall survival rate | 38.4% of passengers survived |
| Female survival rate | 74.2% |
| Male survival rate | 18.9% |
| 1st Class survival | 63.0% |
| 3rd Class survival | 24.2% |
| Child (0-12) survival | ~58% |
| Best outcome | Female, 1st Class — ~97% survival |
| Worst outcome | Male, 3rd Class — ~13% survival |

### 5-Bullet Insight Report
- **Gender dominated**: women were approximately 4x more likely to survive than men — "women and children first" was clearly enforced
- **Class determined lifeboat access**: 1st class passengers survived at 2.6x the rate of 3rd class — upper deck proximity was a literal life-or-death advantage
- **Children were prioritized**: passengers under 12 had a survival rate significantly above the overall average
- **The worst combination**: male 3rd class passengers had the lowest survival rate in the entire dataset at ~13%
- **Missing age is not random**: 177 passengers (19.9%) have no age record — this is likely skewed toward lower-class passengers whose documentation was less thorough

---

## 🧠 Challenges & Learnings

**Challenge:** Age had 177 missing values — nearly 20% of the dataset. Simply dropping these rows would bias the analysis since missing age likely correlates with lower-class passengers. The approach taken was to analyze age where available and flag the missingness as a finding rather than silently imputing values.

**Learning:** EDA is not just about making charts — it is about asking the right questions. The most interesting finding here was not any individual survival rate but the interaction between sex and class. A 1st class female had a ~97% survival rate. A 3rd class male had ~13%. Same ship, same night, completely different outcomes.

**Key insight:** The Titanic data perfectly illustrates how multiple variables interact — no single factor tells the full story. Sex matters, class matters, age matters — but the combination of all three reveals the true picture.

---

## 🔮 Future Improvements

- Build a logistic regression model to predict survival probability using the EDA findings as feature selection guidance
- Add a family size feature (SibSp + Parch + 1) to analyze whether traveling alone vs with family affected survival
- Create an interactive dashboard using Plotly so users can filter by class, sex and age dynamically
- Perform chi-square tests to statistically confirm whether the observed survival differences are significant
- Investigate the `cabin` column — passengers with cabin numbers (mostly 1st class) may have had better lifeboat access

---

## 👩‍💻 Author

**Safva** - Data Science Intern @ Syntecxhub  
🔗 [LinkedIn](https://linkedin.com/in/fathima-safva-578294315) · [GitHub](https://github.com/fsafva13-coder)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).
