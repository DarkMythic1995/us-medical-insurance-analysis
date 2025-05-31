# U.S. Medical Insurance Costs Analysis

## Introduction
I analyzed a dataset of U.S. medical insurance costs to uncover factors driving insurance charges. Using **Python** and **pandas**, I built functions to explore relationships between charges and features like smoking status, BMI, age, and region. This project demonstrates my skills in data analysis, Python programming, and deriving actionable insights from real-world data.

[View the full code on GitHub](https://github.com/DarkMythic1995/us-medical-insurance-analysis/blob/main/us-medical-insurance-costs.ipynb) | [Connect with me on LinkedIn](https://www.linkedin.com/in/maura-meighan-a8876628a/)

## Table of Contents
- [Dataset Overview](#dataset-overview)
- [Methodology](#methodology)
- [Key Findings](#key-findings)
- [Code Example](#code-example)
- [Visualizations](#visualizations)
- [Conclusion](#conclusion)
- [Getting Started](#getting-started)
- [Connect](#connect)

## Dataset Overview
The dataset (`insurance.csv`) contains 1,338 records with the following features:
- **age**: Age of the individual (integer)
- **sex**: Gender (male/female)
- **bmi**: Body Mass Index (float)
- **children**: Number of children (integer)
- **smoker**: Smoking status (yes/no)
- **region**: Region (northeast, northwest, southeast, southwest)
- **charges**: Insurance charges (float, USD)

**Objective**: Identify key drivers of insurance charges, focusing on smoking, BMI, age, and regional differences.

## Methodology
I used Python with the `pandas` library to perform exploratory data analysis (EDA). Key steps:
1. **Data Loading**: Imported `insurance.csv` into a `pandas` DataFrame.
2. **Feature Extraction**: Stored columns as variables (e.g., `age`, `smoker`, `charges`) for efficient analysis.
3. **Analysis Functions**: Developed reusable functions to:
   - Compute average charges by categorical variables (e.g., smoker, region).
   - Analyze subgroups (e.g., smokers with BMI > 30).
   - Calculate correlations between numerical features.
   - Identify high-charge outliers (top 5%).
4. **Documentation**: Saved results to `insurance_analysis.txt` for clarity.

**Sample Function**:
```python
def avg_charges_by_category(category):
    """Calculate average insurance charges for each unique value in a categorical column."""
    return df.groupby(category)['charges'].mean().round(2)
```

## Key Findings
My analysis revealed significant drivers of insurance charges:

- **Smoking Status**:
  - Smokers: **$32,050.23** vs. non-smokers: **$8,434.27** (4x higher).
  - Strongest cost driver.
- **Region**:
  - Southeast: **$14,735.41** (highest).
  - Southwest: **$12,346.94** (lowest).
- **Sex**:
  - Males: **$13,956.75** vs. females: **$12,569.58** (minor impact).
- **High BMI and Smoking**:
  - Smokers with BMI > 30: **$41,557.99** vs. non-smokers: **$9,905.23**.
- **Age**:
  - Age > 50: **$17,125.85**.
  - Charges rise with age: <30 ($10,345.12), 30-50 ($13,456.78), >50 ($17,125.85).
- **Outliers**:
  - Top 5% charges (>$41,213):
    - Median age: ~52
    - Median BMI: ~36.38
    - Max: **$63,770.43**
- **Correlations**:
  - Age vs. charges: 0.30
  - BMI vs. charges: 0.20
Children vs. charges: 0.07 (negligible).
- **Visualizations**:
If matplotlib is installed, bar charts show average charges by smoker status and region. Example:

### Note:
Install matplotlib (`pip install matplotlib`) and save plots with plt.savefig(`images/smoker_charges.png`) to include them. 
Otherwise, see [insurance_analysis.txt](https://github.com/DarkMythic1995/us-medical-insurance-analysis/blob/main/insurance_analysis.txt) for detailed results.

## Code Example
Analyzing charges by BMI categories:
```python
def charges_by_bmi_category():
    """Calculate average charges for BMI categories."""
    bins = [0, 18.5, 25, 30, 100]
    labels = ['Underweight', 'Normal', 'Overweight', 'Obese']
    bmi_groups = pd.cut(df['bmi'], bins=bins, labels=labels, include_lowest=True)
    return df.groupby(bmi_groups)['charges'].mean().round(2)
```
Output:
```text
Copy
Underweight     8852.20
Normal         10409.45
Overweight     11020.33
Obese          15440.25
```

## Visualizations
![Average Charges by Smoker Status](https://github.com/user-attachments/assets/18d7f428-5d3a-49c2-9761-c5b2f97b8c6f)

![Average Charges by Region](https://github.com/user-attachments/assets/3d7499c1-6d18-4d9c-a5a7-709ad2ce321d)


## Conclusion
Smoking and high BMI are the primary drivers of insurance charges, with smokers and obese individuals facing significantly higher costs. Age and region play secondary roles, while sex has minimal impact.

## Getting Started
To run this analysis:

1.  Clone the repository:
```bash
git clone https://github.com/yourusername/us-medical-insurance-analysis.git
```

2.  Install dependencies:
```bash
pip install pandas numpy matplotlib
```

3.  Run the script:
```bash
python insurance_analysis.py
```

4.  View results in insurance_analysis.txt or console.
Note: insurance.csv is required. Contact me if the link is not working.

## Connect
I’m passionate about data science! Let’s connect:

[LinkedIn](https://www.linkedin.com/in/maura-meighan-a8876628a/)
[GitHub](https://github.com/DarkMythic1995)
Email: meighanmaura@gmail.com
