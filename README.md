
# 📊 Marketing Mix Modeling & Media Optimization

**Silver → Gold Dataset | Fox Corporation Data Science Test**

This project performs **Marketing Mix Modeling (MMM)** to quantify the impact of Network TV, Cable TV, and Digital spend on **True Viewership** and **Revenue**. It includes data cleaning, feature engineering, advanced media transformations, model building, simulation, and media budget optimization.

This repository contains:

* `Silver___Gold (2).ipynb` — Full notebook with data processing, modeling, simulation, and optimization
* `Marketing Mix Modeling and Media Optimization.pdf` — Final written report summarizing the project, results, and insights
* `README.md` — (this file)

---

## 📁 Project Structure

```
📂 project/
 ├── Silver___Gold (2).ipynb          # Full analysis, EDA, modeling, simulation, optimization  
 ├── Marketing Mix Modeling...pdf     # Final professional report  
 └── README.md                        # GitHub documentation
```

---

# 🧠 Project Overview

### 🎯 **Objective**

Build a robust MMM to:

1. Quantify the impact of **Network TV**, **Cable TV**, and **Digital** spend
2. Incorporate realistic media behaviors:

   * **Adstock (carryover)**
   * **Hill saturation (diminishing returns)**
   * **Lagged viewership (inertia)**
3. Simulate the effect of a **+20% Digital spend** scenario
4. Optimize weekly media allocation to **maximize predicted viewership**

---

# 🧹 1. Data Processing & Cleaning

### **Silver Dataset → Weekly Gold Dataset**

The episode-level dataset is aggregated to weekly level using:

* Sum of media spend & impressions
* Mean viewership & revenue
* Holiday flag (max in week)
* Lead-in average

Performed multiple quality checks:

* Missing values
* Data types
* Duplicates
* Numeric coercion
* Outlier distributions

---

# ⚙️ 2. Feature Engineering

### ✔ **Adstock Transformation**

Models media carryover using decay values (0.1–0.9).
Best decay selected: **0.7**

### ✔ **Hill Saturation Curve**

Captures diminishing returns at high spend levels.

### ✔ **Lagged Viewership**

Captures audience persistence:
`Lag_Viewership = True_Viewership.shift(1)`

### ✔ **Show, Holiday & Lead-in control variables**

---

# 📈 3. Modeling

Five model families were built:

### **1️⃣ Episode-Level Baseline OLS**

* R² ≈ 0.50
* Media channels positive & significant

### **2️⃣ Weekly Adstock Model**

* R² ≈ 0.86

### **3️⃣ Weekly Adstock + Lag Model**

* R² ≈ 0.979
* Lag term strongly improves fit

### **4️⃣ Hill Saturation + Lag Model**

* R² ≈ 0.967

### **5️⃣ Final Adsat (Adstock + Saturation) + Lag Model**

**R² = 0.984 | Adj R² = 0.970**
Used as primary scenario & optimization engine.

---

# 🚀 4. Simulation: +20% Digital Spend

Simulated Digital spend increase for Weeks **5–10**.

**Results:**

* Predicted viewership increases only within intervention period
* Saturation & adstock create non-linear uplift
* Good for launching high-priority weeks or special episodes

---

# 🎯 5. Media Mix Optimization

Performed a grid-search optimization for **Week 8** under a fixed total budget.

### **Optimal Allocation:**

* **60% Network TV**
* **0% Cable TV**
* **40% Digital**
* Predicted Viewership: **~97.1M**

---

# 🧩 6. Final Insights

### **Key Takeaways**

* Network TV & Digital are the strongest channels
* Cable TV yields diminishing incremental returns
* Viewership has strong inertia → lag must be modeled
* Digital spend should be increased **strategically**, not uniformly
* Lead-in & Holiday scheduling materially impact viewership

### **Limitations**

* Only ~14 valid grouped weekly observations in final model
* Model is best for simulation & planning, not causal inference
* More seasons/weeks improve stability

---

# 📘 How to Run the Notebook

### **Requirements**

* Python 3.8+
* pandas, numpy
* statsmodels
* matplotlib
* seaborn (optional)

### **Usage**

```bash
jupyter notebook "Silver___Gold (2).ipynb"
```

---

# 📝 Author

**Vandana Bhumireddygari**
Master’s in Data Science & AI — UT Dallas
(2025)

---

If you want, I can also:

✅ Add badges (Python version, license, last updated)
✅ Add visuals / diagrams inside the README
✅ Generate a GitHub-ready **repo landing page** screenshot
✅ Create a polished repository description text for GitHub sidebar

Just tell me!
