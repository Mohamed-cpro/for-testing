# 🛒 Market Basket Analysis — Task 1

A complete implementation of **Market Basket Analysis** using the **Apriori algorithm** on a real retail transaction dataset.

---

## 📁 Project Files

| File | Description |
|------|-------------|
| `Market_Basket_Analysis.ipynb` | Main notebook with all analysis steps |
| `Market_Basket_Optimisation.csv` | Raw transaction dataset (7,501 transactions) |
| `frequent_itemsets.csv` | Output — all frequent itemsets found by Apriori |
| `association_rules.csv` | Output — all association rules sorted by Lift |
| `chart1_item_frequency.png` | Bar chart of top 15 most purchased items |
| `chart2_support_confidence_lift.png` | Scatter plot — Support vs Confidence (bubble = Lift) |
| `chart3_top10_lift.png` | Horizontal bar chart of top 10 rules by Lift |
| `chart4_heatmap.png` | Lift heatmap for top rule pairs |

---

## 📊 Dataset

- **File:** `Market_Basket_Optimisation.csv`
- **Transactions:** 7,501
- **Unique Products:** ~120
- **Format:** No header row; each row = one transaction; items are comma-separated across columns
- **Average basket size:** ~3–4 items per transaction

---

## ⚙️ Requirements

Install the required Python libraries before running the notebook:

```bash
pip install mlxtend pandas numpy matplotlib
```

Or run the first cell in the notebook which handles the installation automatically.

| Library | Version | Purpose |
|---------|---------|---------|
| `mlxtend` | ≥ 0.23 | Apriori algorithm & association rules |
| `pandas` | ≥ 1.5 | Data loading and manipulation |
| `numpy` | ≥ 1.23 | Numerical operations |
| `matplotlib` | ≥ 3.6 | Visualizations |

---

## 🚀 How to Run

1. Place `Market_Basket_Optimisation.csv` and `Market_Basket_Analysis.ipynb` in the **same folder**
2. Open the notebook in Jupyter or VS Code
3. Run all cells from top to bottom (`Kernel > Restart & Run All`)
4. Output CSV files and chart images will be saved in the same folder

---

## 🔍 Analysis Steps

### Step 1 — Install Libraries
Installs `mlxtend` if not already present.

### Step 2 — Load Dataset
Reads the CSV file with no header. Each row is one customer transaction.

### Step 3 — Preprocess (One-Hot Encoding)
Converts raw transaction lists into a boolean matrix using `TransactionEncoder`:
- **Rows** = transactions
- **Columns** = unique products
- **True/False** = whether the product was purchased

### Step 4 — Apply Apriori Algorithm
Finds all **frequent itemsets** — product combinations that appear together often.

```
min_support = 0.02  →  item must appear in ≥ 2% of transactions (~150 out of 7,501)
```

### Step 5 — Generate Association Rules
Produces **if–then rules** from the frequent itemsets (e.g., `{herb & pepper} → {ground beef}`).

```
min_confidence = 0.2  →  rule must be correct at least 20% of the time
```

### Step 6 — Sort by Lift
Rules are sorted by **Lift** (descending) to surface the strongest associations.

### Step 7 — Export to CSV
Saves results to:
- `frequent_itemsets.csv`
- `association_rules.csv`

### Step 8 — Visualizations
Four charts are generated to help interpret the results visually.

---

## 📐 Key Metrics Explained

| Metric | Formula | Good Value | Meaning |
|--------|---------|-----------|---------|
| **Support** | P(A ∩ B) | > 0.02 | How often A and B appear together |
| **Confidence** | P(B \| A) | > 0.3 | When A is bought, how likely is B? |
| **Lift** | Confidence / P(B) | **> 1.5** | Strength of association beyond chance |

> **Lift > 1** = positive association (buying A makes B more likely)  
> **Lift = 1** = no relationship  
> **Lift < 1** = negative association  

---

## 📈 Sample Output

Top association rules discovered (example):

| Antecedent | Consequent | Support | Confidence | Lift |
|-----------|-----------|---------|-----------|------|
| herb & pepper | ground beef | 0.016 | 0.323 | 3.29 |
| light cream | chicken | 0.004 | 0.291 | 4.84 |
| pasta | shrimp | 0.005 | 0.322 | 4.51 |

---

## 💡 Business Applications

- **Store Layout:** Place high-lift product pairs near each other to encourage co-purchases
- **Promotions & Bundles:** Offer discounts on associated items when one is bought
- **Recommendation Engine:** "Customers who bought X also bought Y"
- **Inventory Planning:** Stock associated items together to avoid stockouts

---

## 🔧 Parameter Tuning

| Parameter | Lower Value | Higher Value |
|-----------|------------|-------------|
| `min_support` | More itemsets found, slower | Fewer but more common itemsets |
| `min_confidence` | More rules, less reliable | Fewer rules, more reliable |
| Focus on | — | **Lift > 1.5** for meaningful insights |

---

## 👤 Author

**Task 1 — Data Mining**  
Market Basket Analysis using the Apriori Algorithm
