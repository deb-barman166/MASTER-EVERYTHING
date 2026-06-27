# Python Seaborn — Ultimate Master Guide

> 📘 **The most complete guide to Python Seaborn — from zero to expert.**
>
> 🎯 *Who is this for?* Absolute beginners to advanced data visualizers and ML practitioners.
> ⏱️ *Time to complete:* Self-paced (days to weeks depending on depth)
> 🛠️ *What you'll gain:* Full mastery of statistical data visualization using Seaborn — from quick EDA to publication-quality figures

---

## Table of Contents

1. [🧠 What is Seaborn?](#1-what-is-seaborn-super-simple)
2. [🌍 Why This Exists](#2-why-this-exists)
3. [🧱 Core Fundamentals](#3-core-fundamentals-beginner-level)
4. [⚙️ Complete System Breakdown](#4-complete-system-breakdown)
5. [🔄 Real-World Workflow](#5-real-world-workflow)
6. [🧪 Hands-on Practice](#6-hands-on-practice)
7. [⚠️ Common Mistakes](#7-common-mistakes)
8. [🔥 Pro Tips & Hidden Tricks](#8-pro-tips--hidden-tricks)
9. [🚀 Advanced Concepts](#9-advanced-concepts-expert-level)
10. [🗺️ Complete Roadmap](#10-complete-roadmap)
11. [🧩 Bonus Deep Insights](#11-bonus-deep-insights)
12. [📌 Summary](#12-summary-quick-revision)

---

## 🧠 1. What is Seaborn? (Super Simple)

### The 12-Year-Old Explanation

Imagine you have a big table of data — like a spreadsheet with hundreds of rows about students: their age, scores, gender, city, hours studied, and final grade. Now, you want to *see* the story hidden in that data. Does studying more always lead to better grades? Are scores different across cities? Which subjects are hardest?

Matplotlib can draw charts for you, but you'd have to write lots of code, manually set colors, figure out how to group things, and calculate statistics yourself. **Seaborn** is a Python library that does all of that automatically. You tell it "show me the relationship between hours studied and grade, grouped by gender" — and it draws a beautiful, color-coded chart in one line.

Seaborn is built *on top of* Matplotlib, which means it uses Matplotlib's drawing engine but gives you a much smarter, more convenient way to work — especially with tables of data (called DataFrames).

### Real-Life Analogy

💡 **Think of it like this:**
Matplotlib is like having all the tools in a professional kitchen — pots, pans, knives, ovens. You can cook anything, but you need to know exactly what to do at each step.

Seaborn is like having a **sous chef** who already knows all the classic statistical recipes. You say "make me a correlation heatmap of my DataFrame" and the sous chef handles all the slicing, dicing, and plating — perfectly, every time. You still have the full kitchen (Matplotlib) available when you want to customize the final dish.

### One-Line Definition

> **Seaborn** is a Python statistical data visualization library built on Matplotlib that makes it effortless to create beautiful, informative charts directly from Pandas DataFrames using a high-level, declarative API.

---

## 🌍 2. Why This Exists

### The Problem It Solved

Before Seaborn (created by **Michael Waskom** at Stanford, 2012), visualizing statistical data in Python required:

- Writing 20–50 lines of Matplotlib code to produce what Seaborn does in 1–2 lines
- Manually computing statistical summaries (means, confidence intervals, distributions) before plotting
- Hand-crafting grouped/faceted plots with nested loops
- Manually mapping categorical variables to colors — and maintaining a consistent palette
- No built-in support for complex statistical chart types like violin plots, pair plots, or regression plots with confidence bands

Seaborn solved all of this by baking statistical intelligence directly into the plotting API and providing beautiful defaults that work immediately without customization.

### Where It's Used in the Real World

| Industry / Area          | How Seaborn Is Used                                                           |
|--------------------------|-------------------------------------------------------------------------------|
| Data Science / EDA       | Exploratory Data Analysis — understanding dataset structure in minutes        |
| Machine Learning         | Feature correlation heatmaps, class distribution plots, model residual analysis|
| Academia / Research      | Publication-quality statistical figures for papers and presentations          |
| Healthcare Analytics     | Patient outcome distributions, treatment group comparisons, survival curves   |
| Finance                  | Return distributions, correlation matrices of assets, risk factor analysis    |
| Business Intelligence    | Customer segmentation plots, sales trend comparisons by category/region       |
| Climate Science          | Temperature anomaly heatmaps, multi-variable time series with confidence bands|
| Social Science           | Survey response distributions, demographic comparisons, regression analysis   |

### Why YOU Should Learn It

1. **EDA superpower** — Exploring a new dataset visually is the first step in any ML/Data Science project. Seaborn turns 30-minute Matplotlib sessions into 5-minute Seaborn sessions.
2. **Pandas-native** — Seaborn speaks Pandas natively. Pass a DataFrame + column name strings and it handles everything. No array manipulation needed.
3. **Statistical built-in** — Seaborn doesn't just draw data — it computes and visualizes statistics (confidence intervals, regression lines, distributions, kernel density estimates) automatically.
4. **Portfolio quality by default** — Seaborn's default themes look professional without any customization — critical for GitHub portfolios and Kaggle notebooks.
5. **Gateway to ML visualization** — Every serious ML practitioner uses Seaborn for correlation heatmaps, pairplots, and class distribution analysis. It's a core skill, not optional.

---

## 🧱 3. Core Fundamentals (Beginner Level)

> 🎯 *Goal: Build a solid foundation before going deeper.*

---

### Concept 1: Installing and Importing Seaborn

```bash
pip install seaborn
```

Standard imports at the top of every Seaborn script:

```python
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np

# Set a global theme immediately (makes everything look beautiful)
sns.set_theme(style="darkgrid")  # or "whitegrid", "white", "dark", "ticks"
```

The alias `sns` is the universal convention — don't change it.

💡 **Quick test:**
```python
print(sns.__version__)   # e.g., 0.13.2
tips = sns.load_dataset("tips")   # loads a built-in sample dataset
print(tips.head())
```

---

### Concept 2: Built-in Datasets

Seaborn ships with several famous sample datasets — perfect for learning without needing your own data:

```python
# List all available datasets
print(sns.get_dataset_names())
# Output: ['anagrams', 'anscombe', 'attention', 'brain_networks', 'car_crashes',
#          'diamonds', 'dots', 'dowjones', 'exercise', 'flights', 'fmri',
#          'geyser', 'glue', 'healthexp', 'iris', 'mpg', 'penguins',
#          'planets', 'seaice', 'taxis', 'tips', 'titanic']

# Load common ones
tips     = sns.load_dataset("tips")      # restaurant tips (244 rows)
iris     = sns.load_dataset("iris")      # flower measurements (150 rows)
titanic  = sns.load_dataset("titanic")   # passenger survival data (891 rows)
penguins = sns.load_dataset("penguins")  # penguin measurements (344 rows)
flights  = sns.load_dataset("flights")   # monthly airline passengers (144 rows)
diamonds = sns.load_dataset("diamonds")  # diamond price/quality (53940 rows)

# Explore the dataset
print(tips.shape)         # (244, 7)
print(tips.dtypes)        # column types
print(tips.describe())    # statistical summary
print(tips.head())        # first 5 rows
```

These datasets are used throughout all Seaborn documentation and tutorials — learn them well.

---

### Concept 3: The Seaborn API — How Every Function Works

Every Seaborn plot function shares a consistent pattern:

```python
sns.plot_type(
    data=df,         # your Pandas DataFrame
    x="col_name",   # column for x-axis
    y="col_name",   # column for y-axis
    hue="col_name", # column that controls COLOR (splits data into groups)
    style="col_name",# column that controls line style/marker shape
    size="col_name", # column that controls point/line size
    palette="name",  # color scheme to use
    ax=ax            # optional: which Matplotlib axes to draw on
)
plt.show()
```

The most important parameter to understand is **`hue`** — it's Seaborn's superpower. It takes one column and automatically splits all the data by that column's unique values, coloring each group differently and adding a legend. No loops, no manual color assignment.

💡 **Example:**
```python
tips = sns.load_dataset("tips")

# Without hue: one scatter plot
sns.scatterplot(data=tips, x="total_bill", y="tip")

# With hue: automatically colored by gender — two groups!
sns.scatterplot(data=tips, x="total_bill", y="tip", hue="sex")
plt.show()
```

---

### Concept 4: Your First Real Seaborn Plots

```python
tips = sns.load_dataset("tips")

# ── Scatter plot ──────────────────────────────────────────
sns.scatterplot(data=tips, x="total_bill", y="tip",
                hue="time", style="sex", s=80)
plt.title("Tips vs Total Bill")
plt.show()

# ── Line plot ─────────────────────────────────────────────
flights = sns.load_dataset("flights")
yearly  = flights.groupby("year")["passengers"].sum().reset_index()
sns.lineplot(data=yearly, x="year", y="passengers", marker="o")
plt.title("Annual Air Passengers")
plt.show()

# ── Bar plot ──────────────────────────────────────────────
# sns.barplot shows MEAN + 95% confidence interval automatically!
sns.barplot(data=tips, x="day", y="total_bill", hue="sex",
            palette="muted", capsize=0.1)
plt.title("Average Bill by Day and Gender")
plt.show()

# ── Box plot ──────────────────────────────────────────────
sns.boxplot(data=tips, x="day", y="total_bill", hue="smoker",
            palette="Set2")
plt.title("Bill Distribution by Day")
plt.show()

# ── Histogram ─────────────────────────────────────────────
sns.histplot(data=tips, x="total_bill", hue="time",
             bins=20, kde=True)  # kde=True adds smooth curve overlay
plt.title("Bill Amount Distribution")
plt.show()
```

---

### Concept 5: Themes and Styles

Seaborn has a theme system that sets the visual style of every plot:

```python
# Set theme ONCE at the top — affects all subsequent plots
sns.set_theme(style="darkgrid")    # dark background with grid
sns.set_theme(style="whitegrid")   # white background with grid (default in many contexts)
sns.set_theme(style="white")       # clean white, no grid
sns.set_theme(style="dark")        # dark background, no grid
sns.set_theme(style="ticks")       # white with tick marks

# Set context (scales all text and line sizes for the medium)
sns.set_context("paper")           # smallest — for academic papers
sns.set_context("notebook")        # default — for Jupyter notebooks
sns.set_context("talk")            # larger — for presentations/slides
sns.set_context("poster")          # largest — for printed posters

# Combine both
sns.set_theme(style="whitegrid", context="talk", palette="deep")
```

💡 **Best practice:** Always call `sns.set_theme()` at the very top of your script or notebook, before any plotting. It sets the global aesthetic for all Seaborn AND Matplotlib plots in that session.

---

### Concept 6: Color Palettes

Color is critical for readability and storytelling in data visualization:

```python
# ── Qualitative palettes (for categorical data — distinct colors) ──
sns.set_palette("deep")      # Seaborn's classic 10 colors
sns.set_palette("muted")     # softer version of deep
sns.set_palette("pastel")    # light, soft colors
sns.set_palette("bright")    # vivid, saturated
sns.set_palette("dark")      # darker tones
sns.set_palette("colorblind") # colorblind-accessible (ALWAYS use for presentations)
sns.set_palette("tab10")     # Matplotlib's default 10-color cycle
sns.set_palette("Set1")      # bold, contrasting
sns.set_palette("Set2")      # softer Set1
sns.set_palette("Paired")    # 12 colors in paired light/dark

# ── Sequential palettes (for ordered/numeric data) ──
sns.set_palette("Blues")
sns.set_palette("viridis")
sns.set_palette("rocket")    # Seaborn's own perceptually uniform dark palette
sns.set_palette("mako")      # blue-green to cream
sns.set_palette("flare")     # orange-red

# ── Diverging palettes (for data with meaningful center/zero) ──
sns.set_palette("coolwarm")
sns.set_palette("RdBu")
sns.set_palette("vlag")

# ── Per-plot palette override ──
sns.barplot(data=tips, x="day", y="tip", palette="rocket")

# ── Preview a palette ──
sns.palplot(sns.color_palette("deep", 10))
plt.show()
```

---

🧪 **Mini Task 1:**
> Load the `penguins` dataset. Create a scatter plot of `bill_length_mm` vs `bill_depth_mm`, colored by `species` and shaped by `sex`. Add a title and axis labels.
> ✅ *Expected outcome:* A clean scatter plot with 3 colored species groups and 2 marker shapes, automatic legend.

🧪 **Mini Task 2:**
> Load the `titanic` dataset. Create a bar plot showing average `fare` by passenger `class`, colored by `sex`. Use the `"muted"` palette.
> ✅ *Expected outcome:* Grouped bars per class, two colors for gender, with automatic confidence interval caps.

---

## ⚙️ 4. Complete System Breakdown

> 🎯 *Goal: Understand ALL parts of Seaborn — nothing hidden.*

---

### Part 1: Relational Plots — Relationships Between Variables

**What it is:** Plots that show how two or more numeric variables relate to each other.
**Why it matters:** Reveals correlations, trends, and patterns in your data.
**How it works:** Maps numeric x/y to positions; uses hue/style/size for additional dimensions.

```python
tips = sns.load_dataset("tips")

# ── scatterplot: each row = one point ──
sns.scatterplot(
    data=tips, x="total_bill", y="tip",
    hue="time",           # color by meal time
    style="smoker",       # marker shape by smoker status
    size="size",          # marker size by party size
    sizes=(40, 200),      # min/max marker sizes
    alpha=0.8,            # transparency
    palette="deep"
)

# ── lineplot: for ordered/time series data ──
# KEY FEATURE: lineplot AUTOMATICALLY computes mean + 95% CI when
# multiple y values exist at the same x!
fmri = sns.load_dataset("fmri")
sns.lineplot(
    data=fmri, x="timepoint", y="signal",
    hue="region",         # separate line per region
    style="event",        # different dash style per event type
    ci=95,                # confidence interval (default)
    err_style="band"      # "band" (shaded) or "bars" (error bars)
)

# ── relplot: figure-level version (can create subplots via col/row) ──
sns.relplot(
    data=tips, x="total_bill", y="tip",
    hue="smoker", col="time",    # separate column per time of day
    row="sex",                    # separate row per gender
    kind="scatter"
)
plt.show()
```

---

### Part 2: Distribution Plots — Shape of Data

**What it is:** Plots that show how a single variable (or a few) are distributed.
**Why it matters:** Understanding distributions is Step 1 of any EDA or ML project.

```python
tips = sns.load_dataset("tips")
penguins = sns.load_dataset("penguins")

# ── histplot: histogram with optional KDE ──
sns.histplot(
    data=tips, x="total_bill",
    hue="time",
    bins=25,
    kde=True,             # overlay kernel density estimate
    stat="density",       # normalize y-axis to density (not count)
    common_norm=False,    # normalize each group separately
    alpha=0.5,
    element="step"        # "bars" (default), "step", "poly"
)

# ── kdeplot: smooth density estimate only ──
sns.kdeplot(
    data=penguins, x="flipper_length_mm",
    hue="species",
    fill=True,            # shade under the curve
    alpha=0.4,
    linewidth=2,
    bw_adjust=0.8         # bandwidth adjustment (lower = more detail, higher = smoother)
)

# ── ecdfplot: empirical cumulative distribution function ──
sns.ecdfplot(data=tips, x="total_bill", hue="day")

# ── rugplot: tiny tick marks along the axis for each data point ──
sns.rugplot(data=tips, x="total_bill", hue="sex", height=0.05)

# ── displot: figure-level (supports kind="hist", "kde", "ecdf") ──
sns.displot(
    data=penguins, x="flipper_length_mm",
    hue="species", col="sex",
    kind="kde", fill=True, height=4
)
plt.show()
```

---

### Part 3: Categorical Plots — Categorical vs Numeric

**What it is:** Plots that compare a numeric variable across categories.
**Why it matters:** Essential for group comparisons — the core of most business and scientific analysis.

```python
tips = sns.load_dataset("tips")

# ── stripplot: shows every data point ──
sns.stripplot(data=tips, x="day", y="total_bill", hue="sex",
              jitter=True, dodge=True, alpha=0.6)

# ── swarmplot: like stripplot but no overlapping points ──
sns.swarmplot(data=tips, x="day", y="total_bill", hue="sex",
              dodge=True, size=4)

# ── boxplot: median, IQR, whiskers, outliers ──
sns.boxplot(data=tips, x="day", y="total_bill",
            hue="smoker", palette="Set3",
            width=0.6, linewidth=1.5,
            flierprops=dict(marker='o', markerfacecolor='red', markersize=5))

# ── violinplot: boxplot + KDE shape ──
sns.violinplot(data=tips, x="day", y="total_bill",
               hue="sex", split=True,   # split=True shows both sides together
               palette="muted", inner="quartile")

# ── boxenplot: enhanced boxplot for larger datasets ──
diamonds = sns.load_dataset("diamonds")
sns.boxenplot(data=diamonds, x="cut", y="price", palette="rocket")

# ── barplot: mean + CI per category ──
sns.barplot(data=tips, x="day", y="total_bill",
            hue="sex", palette="deep",
            capsize=0.1, errwidth=1.5,
            estimator="mean", errorbar=("ci", 95))

# ── countplot: counts of occurrences per category ──
sns.countplot(data=tips, x="day", hue="sex",
              palette="pastel", edgecolor="black", linewidth=0.8)

# ── pointplot: mean + CI shown as points connected by lines ──
sns.pointplot(data=tips, x="day", y="total_bill",
              hue="sex", dodge=0.3,
              markers=["o", "s"], linestyles=["-", "--"])

# ── catplot: figure-level (supports all categorical kinds) ──
sns.catplot(data=tips, x="day", y="total_bill",
            hue="smoker", col="time",
            kind="violin", split=True, height=5)
plt.show()
```

---

### Part 4: Regression Plots — Trends and Relationships

**What it is:** Plots that show linear (or polynomial) regression fits with confidence intervals.
**Why it matters:** Instantly visualizes whether two variables have a linear relationship.

```python
tips = sns.load_dataset("tips")

# ── regplot: scatter + regression line + CI band ──
sns.regplot(
    data=tips, x="total_bill", y="tip",
    scatter_kws={"alpha": 0.5, "s": 40},  # scatter point styling
    line_kws={"color": "red", "lw": 2},   # regression line styling
    ci=95,                                  # confidence interval band
    order=1                                 # 1=linear, 2=quadratic, etc.
)

# ── lmplot: figure-level regplot (supports hue, col, row) ──
sns.lmplot(
    data=tips, x="total_bill", y="tip",
    hue="smoker",        # separate regression line per smoker status
    col="time",          # separate subplot per time
    aspect=1.2,          # subplot width/height ratio
    scatter_kws={"alpha": 0.4}
)

# ── residplot: residuals of regression (for model diagnostics) ──
sns.residplot(data=tips, x="total_bill", y="tip",
              lowess=True, color="steelblue")
plt.show()
```

---

### Part 5: Matrix Plots — Grid-Based Visualizations

**What it is:** Plots that display data in a 2D matrix format, typically for correlations or heatmaps.
**Why it matters:** Correlation heatmaps are THE most important diagnostic for feature selection in ML.

```python
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

flights  = sns.load_dataset("flights")
penguins = sns.load_dataset("penguins")

# ── heatmap: matrix of values as colors ──
# Classic: correlation matrix of numeric features
corr = penguins.select_dtypes("number").corr()
mask = np.triu(np.ones_like(corr, dtype=bool))  # mask upper triangle

sns.heatmap(
    corr,
    mask=mask,              # show only lower triangle (avoids redundancy)
    annot=True,             # write numeric values inside cells
    fmt=".2f",              # format of annotations
    cmap="coolwarm",        # diverging colormap (red=positive, blue=negative)
    vmin=-1, vmax=1,        # fix color scale to [-1, 1]
    center=0,               # center color scale at 0
    linewidths=0.5,         # grid lines between cells
    linecolor="white",
    square=True,            # make cells square
    cbar_kws={"shrink": 0.8}
)
plt.title("Feature Correlation Heatmap", fontsize=14, fontweight="bold")

# ── heatmap for pivot tables ──
flights_pivot = flights.pivot_table(
    values="passengers", index="month", columns="year"
)
sns.heatmap(flights_pivot, annot=True, fmt="d", cmap="YlOrRd",
            linewidths=0.3, cbar_kws={"label": "Passengers"})
plt.title("Monthly Flights Heatmap")

# ── clustermap: heatmap + hierarchical clustering (reorders rows/cols) ──
sns.clustermap(
    corr,
    annot=True, fmt=".2f",
    cmap="coolwarm", center=0,
    figsize=(8, 8),
    method="average",       # clustering linkage method
    metric="euclidean"
)
plt.show()
```

---

### Part 6: Multi-Plot Grids — Pair and Facet Plots

**What it is:** Automatically creates a matrix of subplots — one per variable pair or per category.
**Why it matters:** The fastest way to understand an entire dataset's structure at once.

```python
penguins = sns.load_dataset("penguins")
tips     = sns.load_dataset("tips")

# ── pairplot: scatter matrix of ALL numeric variables ──
# Diagonal shows distribution of each variable
# Off-diagonal shows scatter between pairs
sns.pairplot(
    penguins,
    hue="species",             # color by species
    vars=["bill_length_mm", "bill_depth_mm", "flipper_length_mm", "body_mass_g"],
    kind="scatter",            # "scatter", "kde", "hist", "reg"
    diag_kind="kde",           # "auto", "hist", "kde"
    plot_kws={"alpha": 0.5},
    diag_kws={"fill": True},
    corner=True                # show only lower triangle (faster)
)

# ── FacetGrid: manually create a grid of plots per category ──
g = sns.FacetGrid(tips, col="time", row="smoker", height=4, aspect=1.2)
g.map_dataframe(sns.scatterplot, x="total_bill", y="tip", alpha=0.6)
g.add_legend()
g.set_axis_labels("Total Bill ($)", "Tip ($)")
g.set_titles(col_template="{col_name} Meal", row_template="Smoker: {row_name}")

# ── JointGrid / jointplot: scatter + marginal distributions ──
sns.jointplot(
    data=penguins,
    x="bill_length_mm", y="bill_depth_mm",
    hue="species",
    kind="scatter",     # "scatter", "kde", "hist", "hex", "reg", "resid"
    height=7
)
plt.show()
```

---

### 📊 Full Overview Table

| Function / Class      | Category      | Key Feature                                          | Figure-Level? |
|-----------------------|---------------|------------------------------------------------------|---------------|
| `sns.scatterplot()`   | Relational    | x/y scatter with hue/style/size encoding             | No (use `relplot`) |
| `sns.lineplot()`      | Relational    | Auto mean + CI aggregation over time/ordered x       | No (use `relplot`) |
| `sns.relplot()`       | Relational    | Figure-level: scatter or line with col/row faceting  | ✅ Yes        |
| `sns.histplot()`      | Distribution  | Histogram + optional KDE + stat normalization        | No (use `displot`) |
| `sns.kdeplot()`       | Distribution  | Smooth density curves with fill and bandwidth control| No (use `displot`) |
| `sns.ecdfplot()`      | Distribution  | Cumulative distribution function                     | No (use `displot`) |
| `sns.displot()`       | Distribution  | Figure-level: hist/kde/ecdf with col/row faceting    | ✅ Yes        |
| `sns.boxplot()`       | Categorical   | Median + IQR + whiskers + outliers                   | No (use `catplot`) |
| `sns.violinplot()`    | Categorical   | Boxplot + KDE shape; split option for hue            | No (use `catplot`) |
| `sns.barplot()`       | Categorical   | Mean + CI bars per category                          | No (use `catplot`) |
| `sns.countplot()`     | Categorical   | Count of observations per category                   | No (use `catplot`) |
| `sns.stripplot()`     | Categorical   | Individual points per category with jitter           | No (use `catplot`) |
| `sns.swarmplot()`     | Categorical   | Non-overlapping individual points per category       | No (use `catplot`) |
| `sns.pointplot()`     | Categorical   | Mean + CI as connected points                        | No (use `catplot`) |
| `sns.catplot()`       | Categorical   | Figure-level: any categorical kind + col/row         | ✅ Yes        |
| `sns.regplot()`       | Regression    | Scatter + regression line + CI band                  | No (use `lmplot`) |
| `sns.lmplot()`        | Regression    | Figure-level regplot with hue/col/row                | ✅ Yes        |
| `sns.heatmap()`       | Matrix        | Color-encoded matrix, annotations, masking           | No            |
| `sns.clustermap()`    | Matrix        | Heatmap + hierarchical clustering dendrogram         | ✅ Yes        |
| `sns.pairplot()`      | Multi-plot    | All variable-pair scatter matrix + diagonal dists    | ✅ Yes        |
| `sns.jointplot()`     | Multi-plot    | Bivariate scatter + marginal univariate distributions| ✅ Yes        |
| `sns.FacetGrid`       | Multi-plot    | Manually map any function across a grid of subplots  | ✅ Yes        |

---

## 🔄 5. Real-World Workflow

> 🎯 *Goal: See exactly how Seaborn is used step-by-step in practice.*

### 🟢 Beginner Workflow

```
Step 1 → Import seaborn, matplotlib, pandas
Step 2 → Set theme: sns.set_theme()
Step 3 → Load data (sns.load_dataset() or pd.read_csv())
Step 4 → Quick explore: .head(), .dtypes, .describe()
Step 5 → Choose your plot type based on what you want to know
Step 6 → Call the Seaborn function: sns.plottype(data=df, x="col", y="col")
Step 7 → Add title: plt.title() / set axis labels
Step 8 → plt.show() or plt.savefig()
```

**Explanation of each step:**

1. **Import** — `import seaborn as sns` is always first. You'll also need `matplotlib.pyplot as plt` for `plt.show()` and fine-tuning.
2. **Set theme** — `sns.set_theme(style="whitegrid")` at the top makes ALL your plots beautiful instantly.
3. **Load data** — Start with `sns.load_dataset("tips")` while learning. Switch to `pd.read_csv("your_file.csv")` for real work.
4. **Explore** — Before plotting, understand your data: how many rows? What columns? What types? Any missing values?
5. **Choose plot** — Match chart type to your question: *distribution?* → `histplot/kdeplot`. *Relationship?* → `scatterplot`. *Groups?* → `boxplot/barplot`. *Everything?* → `pairplot`.
6. **Call function** — Seaborn's `data=df, x="col"` pattern means you never need to extract arrays manually.
7. **Label** — `plt.title()` and `ax.set_xlabel()` are non-negotiable for any real figure.
8. **Output** — `plt.show()` for interactive viewing; `plt.savefig("fig.png", dpi=200, bbox_inches="tight")` for saving.

---

### 🔵 Professional Workflow

```
Step 1  → sns.set_theme(style, context, palette, font) — full branding
Step 2  → Load real data from CSV/SQL/API into Pandas DataFrame
Step 3  → Data cleaning: handle NaN, convert dtypes, engineer features
Step 4  → Full EDA pipeline:
          → histplot/kdeplot for each numeric feature
          → countplot for each categorical feature
          → heatmap of correlation matrix
          → pairplot for multivariate overview
Step 5  → Targeted analysis: regplot / lmplot / catplot with hue splits
Step 6  → Fine-tune: combine with Matplotlib (ax returned by Seaborn)
          → Custom tick labels, annotations, spine removal
Step 7  → Figure-level plots (relplot, catplot, displot) for facet grids
Step 8  → plt.tight_layout() + plt.savefig(dpi=300, bbox_inches="tight")
Step 9  → Embed figures in Jupyter notebook, report, or dashboard
```

**What makes this different:**
Professionals treat visualization as a *pipeline*, not individual charts. They have a standardized EDA function they run on every new dataset. They use `fig.savefig()` with consistent DPI. They customize Seaborn output via the returned `ax` object for pixel-perfect control. They never use default titles — every figure has a meaningful, audience-facing title.

---

## 🧪 6. Hands-on Practice

> 🎯 *Goal: Apply what you've learned through real projects.*

---

### 🟢 Beginner Project: Titanic Survival Explorer

**Goal:** Visually explore the Titanic dataset to understand which factors affected survival.
**Estimated Time:** 45 minutes
**Skills Used:** `countplot`, `barplot`, `histplot`, `boxplot`, `hue`, `catplot`, themes

**Instructions:**

1. Load the Titanic dataset
2. Answer 4 visual questions about survival patterns
3. Use a 2×2 subplot layout
4. Apply a consistent theme and palette

```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.set_theme(style="whitegrid", context="notebook", palette="deep")

titanic = sns.load_dataset("titanic")

fig, axes = plt.subplots(2, 2, figsize=(14, 10))
fig.suptitle("Titanic Survival Analysis", fontsize=18, fontweight="bold", y=1.01)

# Q1: Survival count by gender
sns.countplot(data=titanic, x="sex", hue="survived",
              palette=["#E74C3C", "#2ECC71"], ax=axes[0, 0])
axes[0, 0].set_title("Survival by Gender")
axes[0, 0].set_xlabel("Gender")
axes[0, 0].set_ylabel("Count")
axes[0, 0].legend(["Did Not Survive", "Survived"])

# Q2: Average age by class and survival
sns.barplot(data=titanic, x="pclass", y="age",
            hue="survived", palette="muted",
            capsize=0.1, ax=axes[0, 1])
axes[0, 1].set_title("Average Age by Class & Survival")
axes[0, 1].set_xlabel("Passenger Class")
axes[0, 1].set_ylabel("Average Age")

# Q3: Fare distribution by class
sns.boxplot(data=titanic, x="pclass", y="fare",
            hue="survived", palette="Set2", ax=axes[1, 0])
axes[1, 0].set_ylim(0, 300)
axes[1, 0].set_title("Fare Distribution by Class & Survival")
axes[1, 0].set_xlabel("Passenger Class")
axes[1, 0].set_ylabel("Fare ($)")

# Q4: Age distribution by survival
sns.kdeplot(data=titanic, x="age", hue="survived",
            fill=True, alpha=0.4, linewidth=2,
            palette=["#E74C3C", "#2ECC71"], ax=axes[1, 1])
axes[1, 1].set_title("Age Distribution by Survival")
axes[1, 1].set_xlabel("Age")
axes[1, 1].set_ylabel("Density")

plt.tight_layout()
plt.savefig("titanic_explorer.png", dpi=150, bbox_inches="tight")
plt.show()
print("Insight: Women and children in first class had highest survival rates.")
```

✅ **You've succeeded when:** You have a 4-panel dashboard answering 4 different survival questions, saved as `titanic_explorer.png`.

---

### 🔵 Intermediate Project: Penguins Full EDA Dashboard

**Goal:** Perform a complete Exploratory Data Analysis on the penguins dataset using 6 different Seaborn plot types in a professional layout.
**Estimated Time:** 2–3 hours
**Skills Used:** `pairplot`, `heatmap`, `violinplot`, `kdeplot`, `jointplot`, `countplot`, custom styling

**Instructions:**

1. Load and clean the penguins dataset (drop NaN rows)
2. Build a complete EDA with: overview pairplot, correlation heatmap, per-feature distributions, bivariate analysis, species counts
3. Apply a dark, professional theme

```python
import seaborn as sns
import matplotlib.pyplot as plt
import numpy as np

sns.set_theme(style="darkgrid", context="notebook")
penguins = sns.load_dataset("penguins").dropna()

SPECIES_PALETTE = {"Adelie": "#E74C3C", "Chinstrap": "#3498DB", "Gentoo": "#2ECC71"}

# ── Plot 1: Pairplot (full multivariate overview) ──
pair = sns.pairplot(
    penguins,
    hue="species", palette=SPECIES_PALETTE,
    vars=["bill_length_mm", "bill_depth_mm", "flipper_length_mm", "body_mass_g"],
    diag_kind="kde", kind="scatter",
    plot_kws={"alpha": 0.5, "s": 30},
    diag_kws={"fill": True, "linewidth": 1.5},
    corner=True
)
pair.fig.suptitle("Penguin Species — Feature Pairplot", y=1.01, fontsize=14, fontweight="bold")
plt.savefig("penguin_pairplot.png", dpi=150, bbox_inches="tight")
plt.show()

# ── Plot 2: Correlation Heatmap ──
numeric_cols = ["bill_length_mm", "bill_depth_mm", "flipper_length_mm", "body_mass_g"]
corr = penguins[numeric_cols].corr()
mask = np.triu(np.ones_like(corr, dtype=bool))

fig, ax = plt.subplots(figsize=(8, 6))
sns.heatmap(
    corr, mask=mask, annot=True, fmt=".2f",
    cmap="coolwarm", center=0, vmin=-1, vmax=1,
    square=True, linewidths=1, linecolor="white",
    cbar_kws={"shrink": 0.75, "label": "Pearson r"},
    ax=ax
)
ax.set_title("Feature Correlation Matrix — Penguins", fontsize=13, fontweight="bold")
plt.tight_layout()
plt.savefig("penguin_corr.png", dpi=150, bbox_inches="tight")
plt.show()

# ── Plot 3: 2×2 Feature Distributions by Species ──
fig, axes = plt.subplots(2, 2, figsize=(13, 9))
fig.suptitle("Feature Distributions by Penguin Species", fontsize=15, fontweight="bold")

features = ["bill_length_mm", "bill_depth_mm", "flipper_length_mm", "body_mass_g"]
titles   = ["Bill Length (mm)", "Bill Depth (mm)", "Flipper Length (mm)", "Body Mass (g)"]

for ax, feat, title in zip(axes.flat, features, titles):
    sns.violinplot(
        data=penguins, x="species", y=feat,
        palette=SPECIES_PALETTE, inner="quartile",
        linewidth=1.5, ax=ax
    )
    sns.stripplot(
        data=penguins, x="species", y=feat,
        palette=SPECIES_PALETTE, size=3,
        alpha=0.4, ax=ax, dodge=False
    )
    ax.set_title(title)
    ax.set_xlabel("")

plt.tight_layout()
plt.savefig("penguin_distributions.png", dpi=150, bbox_inches="tight")
plt.show()

# ── Plot 4: Jointplot (bivariate bill analysis) ──
jp = sns.jointplot(
    data=penguins,
    x="bill_length_mm", y="bill_depth_mm",
    hue="species", palette=SPECIES_PALETTE,
    kind="scatter", height=7,
    marginal_kws={"fill": True, "alpha": 0.4}
)
jp.set_axis_labels("Bill Length (mm)", "Bill Depth (mm)", fontsize=12)
jp.figure.suptitle("Bill Dimensions by Species", y=1.01, fontsize=13, fontweight="bold")
plt.savefig("penguin_joint.png", dpi=150, bbox_inches="tight")
plt.show()
```

✅ **You've succeeded when:** You have 4 separate, professional-quality figures (pairplot, heatmap, violin distributions, jointplot) that together tell the complete story of the penguin dataset.

---

### 🔴 Advanced Project: ML Feature Analysis Dashboard

**Goal:** Build a production-quality, comprehensive ML feature analysis dashboard for a classification dataset, including correlation heatmaps, class distributions, feature importance visualization, and model diagnostics — all in Seaborn.
**Estimated Time:** 1 day

**Feature Set:**
- Correlation matrix with hierarchical clustering (`clustermap`)
- Class balance bar chart
- Per-feature distribution split by class (FacetGrid)
- Regression residuals
- Feature pair analysis with regression overlays

```python
import seaborn as sns
import matplotlib.pyplot as plt
import matplotlib.gridspec as gridspec
import pandas as pd
import numpy as np
from sklearn.datasets import load_breast_cancer
from sklearn.preprocessing import StandardScaler

# ── Load and prep dataset ──
data = load_breast_cancer()
df = pd.DataFrame(data.data, columns=data.feature_names)
df["target"] = data.target
df["diagnosis"] = df["target"].map({0: "Malignant", 1: "Benign"})

# Select top 8 features for clarity
top_features = list(data.feature_names[:8])

# ── Custom dark palette ──
DIAG_PALETTE = {"Malignant": "#FF4B4B", "Benign": "#00C9A7"}
sns.set_theme(style="dark", context="notebook")
plt.rcParams.update({"figure.facecolor": "#1a1a2e", "axes.facecolor": "#16213e",
                     "text.color": "white", "axes.labelcolor": "white",
                     "xtick.color": "white", "ytick.color": "white"})

# ── Panel 1: Class Balance ──
fig1, ax1 = plt.subplots(figsize=(6, 4), facecolor="#1a1a2e")
ax1.set_facecolor("#16213e")
counts = df["diagnosis"].value_counts()
bars = ax1.bar(counts.index, counts.values,
               color=[DIAG_PALETTE[k] for k in counts.index],
               edgecolor="none", width=0.5)
for bar, val in zip(bars, counts.values):
    ax1.text(bar.get_x() + bar.get_width()/2, bar.get_height() + 5,
             str(val), ha="center", va="bottom", color="white", fontweight="bold")
ax1.set_title("Class Distribution", color="white", fontsize=13, fontweight="bold")
ax1.set_ylabel("Count", color="white")
ax1.spines["top"].set_visible(False)
ax1.spines["right"].set_visible(False)
for spine in ax1.spines.values():
    spine.set_edgecolor("#444")
plt.tight_layout()
plt.savefig("ml_class_balance.png", dpi=150, bbox_inches="tight",
            facecolor=fig1.get_facecolor())
plt.show()

# ── Panel 2: Correlation Clustermap ──
corr = df[top_features].corr()
cg = sns.clustermap(
    corr, annot=True, fmt=".2f",
    cmap="coolwarm", center=0, vmin=-1, vmax=1,
    figsize=(10, 8), linewidths=0.5,
    method="average", metric="euclidean",
    cbar_kws={"label": "Pearson r", "shrink": 0.6}
)
cg.fig.suptitle("Feature Correlation Clustermap", fontsize=14,
                fontweight="bold", y=1.01)
plt.savefig("ml_clustermap.png", dpi=150, bbox_inches="tight")
plt.show()

# ── Panel 3: Per-feature KDE by Class ──
df_melt = df[top_features + ["diagnosis"]].melt(
    id_vars="diagnosis", var_name="feature", value_name="value"
)
g = sns.FacetGrid(df_melt, col="feature", hue="diagnosis",
                  col_wrap=4, height=3.5, aspect=1.2,
                  palette=DIAG_PALETTE, sharey=False)
g.map_dataframe(sns.kdeplot, x="value", fill=True, alpha=0.4, linewidth=2)
g.add_legend(title="Diagnosis")
g.set_titles(col_template="{col_name}", size=10)
g.set_axis_labels("Value", "Density")
g.figure.suptitle("Feature Distributions by Diagnosis", fontsize=14,
                  fontweight="bold", y=1.02)
plt.savefig("ml_feature_dists.png", dpi=150, bbox_inches="tight")
plt.show()

# ── Panel 4: Top feature pairplot ──
top4 = top_features[:4]
pg = sns.pairplot(
    df[top4 + ["diagnosis"]],
    hue="diagnosis", palette=DIAG_PALETTE,
    diag_kind="kde", kind="scatter",
    plot_kws={"alpha": 0.4, "s": 20},
    diag_kws={"fill": True},
    corner=True
)
pg.fig.suptitle("Top Feature Pairs by Diagnosis", y=1.01,
                fontsize=14, fontweight="bold")
plt.savefig("ml_pairplot.png", dpi=150, bbox_inches="tight")
plt.show()

print("✅ ML Feature Analysis Dashboard complete — 4 figures saved!")
```

🔥 **Challenge:** Add a 5th panel showing a `pointplot` of the mean (± CI) for each of the 8 features, grouped by diagnosis — all on one chart using `FacetGrid` with a shared y-axis (after StandardScaler normalization).

---

## ⚠️ 7. Common Mistakes

> 🎯 *Goal: Avoid the traps that catch 90% of beginners.*

---

### ❌ Mistake 1: Calling `sns.set_theme()` AFTER Plotting

**Why it happens:** Beginners add theming code after they already wrote some plots.

**What goes wrong:** First plots use ugly defaults; later plots use the theme. Inconsistent appearance.

```python
# ❌ Wrong way:
sns.histplot(data=df, x="col")   # uses ugly default style!
sns.set_theme(style="darkgrid")  # too late — won't affect the histogram above

# ✅ Right way:
sns.set_theme(style="darkgrid")  # ALWAYS first, before any plot
sns.histplot(data=df, x="col")
```

**The Fix:** `sns.set_theme()` is always the very first Seaborn call in your script or notebook cell.

---

### ❌ Mistake 2: Passing Arrays Instead of DataFrame + Column Names

**Why it happens:** Coming from Matplotlib where you pass arrays. Old habit.

**What goes wrong:** You lose Seaborn's automatic labeling, grouping, and legend generation.

```python
# ❌ Wrong way (array-based — no auto labels, no hue support):
tips = sns.load_dataset("tips")
sns.scatterplot(x=tips["total_bill"].values, y=tips["tip"].values)

# ✅ Right way (DataFrame-based — everything automatic):
sns.scatterplot(data=tips, x="total_bill", y="tip", hue="sex")
# → Axis labels auto-set to "total_bill" and "tip"
# → Legend auto-generated for hue groups
```

---

### ❌ Mistake 3: Confusing Axes-Level vs Figure-Level Functions

**Why it happens:** Beginners don't know that some functions return Axes and others return FacetGrid objects.

**What goes wrong:** Trying to use `plt.title()` on a figure-level plot (like `pairplot`) doesn't work as expected. Passing `ax=ax` to a figure-level function causes an error.

```python
# ❌ Wrong way:
g = sns.pairplot(df, hue="species")
plt.title("My Pairplot")   # This puts a title on only the LAST subplot!

# ✅ Right way for figure-level plots:
g = sns.pairplot(df, hue="species")
g.fig.suptitle("My Pairplot", y=1.01, fontsize=14)   # title on the whole figure

# ❌ Wrong way:
fig, ax = plt.subplots()
sns.lmplot(data=df, x="x", y="y", ax=ax)   # ERROR: lmplot creates its own figure!

# ✅ Right way for axes-level:
fig, ax = plt.subplots()
sns.regplot(data=df, x="x", y="y", ax=ax)  # regplot is axes-level, accepts ax=
```

**Rule:** Figure-level = `relplot`, `displot`, `catplot`, `lmplot`, `pairplot`, `jointplot`, `clustermap`. Axes-level = everything else.

---

### ❌ Mistake 4: Not Handling Missing Values Before Plotting

**Why it happens:** Forgetting that NaN values cause silent issues in some plot types.

**What goes wrong:** `pairplot` and `clustermap` silently drop rows with NaN, but `violinplot` can raise errors.

```python
# ❌ Wrong way:
penguins = sns.load_dataset("penguins")
sns.pairplot(penguins, hue="sex")  # 11 rows have NaN — silently dropped!

# ✅ Right way:
penguins_clean = sns.load_dataset("penguins").dropna()
sns.pairplot(penguins_clean, hue="sex")
# OR selectively:
penguins_clean = penguins.dropna(subset=["sex", "flipper_length_mm"])
```

---

### ❌ Mistake 5: Using `barplot` When You Mean `countplot`

**Why it happens:** Both make bar charts, but they measure different things.

**What goes wrong:** `barplot` computes the *mean* of a numeric column. `countplot` counts *occurrences*. Wrong choice = meaningless chart.

```python
# ❌ Wrong way (using barplot to count — gives mean of a number you didn't ask for):
sns.barplot(data=titanic, x="pclass", y="survived")
# → shows MEAN of 'survived' (0/1) = survival RATE, not count

# If you want COUNT of survived passengers per class:
# ✅ Right way 1: countplot
sns.countplot(data=titanic[titanic.survived==1], x="pclass")

# ✅ Right way 2: value_counts + barplot if you need customization
vc = titanic.groupby("pclass")["survived"].sum().reset_index()
sns.barplot(data=vc, x="pclass", y="survived")
```

---

### ❌ Mistake 6: Overloading `hue` with Too Many Categories

**Why it happens:** Thinking more `hue` levels = more information.

**What goes wrong:** 10+ colors in a legend are unreadable — the chart communicates nothing.

```python
# ❌ Wrong way:
sns.scatterplot(data=df, x="x", y="y", hue="country")   # 50 countries = 50 colors!

# ✅ Right way 1: Limit to top N categories
top_countries = df["country"].value_counts().head(5).index
sns.scatterplot(data=df[df["country"].isin(top_countries)],
                x="x", y="y", hue="country")

# ✅ Right way 2: Use FacetGrid (facet) instead of hue when many categories
g = sns.FacetGrid(df, col="region", col_wrap=3)
g.map_dataframe(sns.scatterplot, x="x", y="y")
```

---

### ❌ Mistake 7: Forgetting `plt.show()` / Not Clearing State Between Plots

**Why it happens:** In scripts (not Jupyter), plots accumulate without `plt.show()`.

**What goes wrong:** Multiple plots' elements get drawn on the same figure, creating a mess.

```python
# ❌ Wrong way (in a script):
sns.histplot(data=df, x="col1")
sns.histplot(data=df, x="col2")    # draws ON TOP of col1 plot!
plt.show()                          # shows both overlaid

# ✅ Right way:
sns.histplot(data=df, x="col1")
plt.title("Column 1")
plt.show()     # show and clear

sns.histplot(data=df, x="col2")    # fresh plot
plt.title("Column 2")
plt.show()

# ✅ Even better: use fig, ax explicitly
fig, axes = plt.subplots(1, 2, figsize=(12, 5))
sns.histplot(data=df, x="col1", ax=axes[0])
sns.histplot(data=df, x="col2", ax=axes[1])
plt.show()
```

---

## 🔥 8. Pro Tips & Hidden Tricks

> 🎯 *Goal: Level up with knowledge most tutorials never share.*

---

### 💎 Tip 1: Use `ax` Return Value for Matplotlib Fine-Tuning

Every axes-level Seaborn function returns a Matplotlib `Axes` object, which you can further customize:

```python
tips = sns.load_dataset("tips")

ax = sns.boxplot(data=tips, x="day", y="total_bill",
                 hue="sex", palette="muted")

# Now use ax (Matplotlib) for further customization:
ax.set_title("Tip Analysis", fontsize=15, fontweight="bold", pad=15)
ax.set_xlabel("Day of Week", fontsize=12)
ax.set_ylabel("Total Bill ($)", fontsize=12)
ax.set_xticklabels(["Thursday", "Friday", "Saturday", "Sunday"], rotation=20)
ax.spines["top"].set_visible(False)
ax.spines["right"].set_visible(False)
ax.legend(title="Gender", framealpha=0.8)
ax.yaxis.grid(True, linestyle="--", alpha=0.5)

plt.tight_layout()
plt.show()
```

---

### 💎 Tip 2: Overlay Multiple Seaborn Plots on the Same Axes

```python
fig, ax = plt.subplots(figsize=(10, 6))

# Layer 1: violin (shows distribution shape)
sns.violinplot(data=tips, x="day", y="total_bill",
               inner=None, palette="muted", alpha=0.6, ax=ax)

# Layer 2: boxplot (shows quartiles on top of violin)
sns.boxplot(data=tips, x="day", y="total_bill",
            width=0.15, palette="dark:white", ax=ax,
            linewidth=1.5, fliersize=0)

# Layer 3: strip (shows individual points)
sns.stripplot(data=tips, x="day", y="total_bill",
              size=3, color="black", alpha=0.3, jitter=True, ax=ax)

ax.set_title("Total Bill by Day (Violin + Box + Strip)", fontsize=13)
plt.show()
```

This triple-layer plot is considered best practice in modern statistical visualization — more information density than any single plot type alone.

---

### 💎 Tip 3: Custom Color Palettes from Brand Colors

```python
# Define your own palette from hex colors
my_palette = ["#00C9A7", "#FF4B4B", "#4B9FFF", "#FFB347", "#C39BD3"]
sns.set_palette(my_palette)

# Or create a continuous palette from specific colors
custom_cmap = sns.blend_palette(["#1a1a2e", "#00d4ff", "#ffffff"], as_cmap=True)
sns.heatmap(corr_matrix, cmap=custom_cmap)

# Use diverging palette centered at a specific value
div_pal = sns.diverging_palette(220, 20, as_cmap=True)   # hue: 220=blue, 20=red
sns.heatmap(corr_matrix, cmap=div_pal, center=0)

# Preview multiple palettes at once
fig, axes = plt.subplots(5, 1, figsize=(10, 4))
for ax, name in zip(axes, ["deep", "muted", "rocket", "coolwarm", "viridis"]):
    sns.palplot(sns.color_palette(name, 10), ax=ax)
    ax.set_title(name, fontsize=9)
plt.tight_layout()
plt.show()
```

---

### 💎 Tip 4: `move_legend()` for Perfect Legend Placement

Seaborn 0.12+ includes a helper to reposition legends on figure-level plots:

```python
g = sns.relplot(data=tips, x="total_bill", y="tip",
                hue="time", col="sex", kind="scatter")

# Move legend outside the plot area
sns.move_legend(g, "upper left", bbox_to_anchor=(1, 1),
                title="Meal Time", frameon=True)
plt.show()
```

---

### 💎 Tip 5: `hue_order` and `order` for Controlling Sort Order

By default, Seaborn orders categories alphabetically or by first occurrence. Control it explicitly:

```python
# Specify exact order of categories on x-axis
sns.barplot(data=tips, x="day", y="total_bill",
            order=["Thur", "Fri", "Sat", "Sun"])   # chronological

# Control hue order (legend sequence)
sns.boxplot(data=tips, x="day", y="total_bill",
            hue="sex", hue_order=["Female", "Male"])

# Sort by value (descending)
day_order = tips.groupby("day")["total_bill"].mean().sort_values(ascending=False).index
sns.barplot(data=tips, x="day", y="total_bill", order=day_order)
```

---

### 💎 Tip 6: Add Statistical Annotations with `statannotations`

```bash
pip install statannotations
```

```python
from statannotations.Annotator import Annotator

fig, ax = plt.subplots(figsize=(8, 6))
sns.boxplot(data=tips, x="day", y="total_bill", palette="muted", ax=ax)

# Add p-value annotations between pairs
pairs = [("Thur", "Fri"), ("Sat", "Sun"), ("Fri", "Sat")]
annotator = Annotator(ax, pairs, data=tips, x="day", y="total_bill")
annotator.configure(test="Mann-Whitney", text_format="star", loc="outside")
annotator.apply_and_annotate()

ax.set_title("Bill Comparison with Statistical Tests")
plt.show()
```

This adds `*`, `**`, `***`, or `ns` significance markers above boxplot pairs — standard in academic publications.

---

### 💎 Tip 7: `despine()` — The Most Common Style Improvement

Removing the top and right plot borders instantly makes charts look cleaner and more modern:

```python
ax = sns.histplot(data=tips, x="total_bill", kde=True)
sns.despine()                           # removes top and right spines (default)
sns.despine(left=True, bottom=False)    # remove left spine too
sns.despine(offset=10)                  # offset remaining spines from data area
```

---

### 💎 Tip 8: `FacetGrid.map_dataframe()` with Custom Functions

```python
import seaborn as sns
import matplotlib.pyplot as plt

tips = sns.load_dataset("tips")

# Custom plot function that takes (data, x, y, **kwargs)
def custom_scatter_with_mean(data, x, y, **kwargs):
    ax = plt.gca()
    ax.scatter(data[x], data[y], **kwargs)
    mean_x = data[x].mean()
    mean_y = data[y].mean()
    ax.axvline(mean_x, color="red", linestyle="--", alpha=0.7, lw=1.5)
    ax.axhline(mean_y, color="blue", linestyle="--", alpha=0.7, lw=1.5)
    ax.annotate(f"μx={mean_x:.1f}\nμy={mean_y:.1f}",
                xy=(0.05, 0.95), xycoords="axes fraction",
                fontsize=8, va="top",
                bbox=dict(boxstyle="round", facecolor="wheat", alpha=0.5))

g = sns.FacetGrid(tips, col="time", row="smoker", height=3.5)
g.map_dataframe(custom_scatter_with_mean, x="total_bill", y="tip",
                alpha=0.5, s=30, color="steelblue")
g.add_legend()
g.set_axis_labels("Total Bill ($)", "Tip ($)")
g.set_titles(col_template="{col_name}", row_template="Smoker: {row_name}")
plt.show()
```

---

### 🛠️ Recommended Tools & Resources

| Tool / Resource         | What It's For                                           | Notes                                        |
|-------------------------|---------------------------------------------------------|----------------------------------------------|
| Pandas                  | Data loading and manipulation before Seaborn           | `data=df` is central to Seaborn              |
| Matplotlib              | Fine-tuning Seaborn output, adding elements             | Always available via `ax` returned by Seaborn|
| `statannotations`       | Adding p-value/significance stars to categorical plots  | `pip install statannotations`                |
| `pingouin`              | Statistical tests that pair with Seaborn visualization  | `pip install pingouin`                       |
| Jupyter Notebook        | Interactive EDA environment                             | Best place to use Seaborn                    |
| Seaborn Gallery         | Official example gallery with source code              | seaborn.pydata.org/examples                  |
| Seaborn Tutorial        | Official in-depth tutorial pages                        | seaborn.pydata.org/tutorial                  |
| `scikit-learn` datasets | Realistic ML datasets for advanced Seaborn projects    | `from sklearn.datasets import load_*`        |
| `plotly`                | When you need interactive versions of Seaborn charts   | Different API but complements Seaborn        |

---

## 🚀 9. Advanced Concepts (Expert Level)

> 🎯 *Goal: Go deep into the internals and advanced techniques.*

---

### Advanced Concept 1: Custom FacetGrid with Complex Mappings

FacetGrid is Seaborn's most powerful and flexible tool. Here's how professionals use it:

```python
import seaborn as sns
import matplotlib.pyplot as plt
import scipy.stats as stats
import numpy as np

tips = sns.load_dataset("tips")

# Advanced: map multiple plot types to the same FacetGrid
g = sns.FacetGrid(tips, col="time", row="smoker",
                  height=4, aspect=1.3,
                  margin_titles=True,   # row/col labels in margins
                  sharex=True, sharey=True)

# Map scatter
g.map_dataframe(sns.scatterplot, x="total_bill", y="tip",
                alpha=0.4, s=30, color="steelblue")

# Map regression line on top
g.map_dataframe(sns.regplot, x="total_bill", y="tip",
                scatter=False,   # don't re-draw scatter
                line_kws={"color": "red", "lw": 2})

g.set_axis_labels("Total Bill ($)", "Tip ($)")
g.set_titles(col_template="{col_name} Meal", row_template="Smoker: {row_name}")
g.add_legend()

# Add custom annotations to each panel
for ax_row in g.axes:
    for ax in ax_row:
        ax.set_xlim(0, 55)
        ax.set_ylim(-0.5, 11)

g.figure.suptitle("Tip vs Bill — Faceted by Meal Time & Smoking",
                   y=1.01, fontsize=14, fontweight="bold")
plt.savefig("advanced_facet.png", dpi=150, bbox_inches="tight")
plt.show()
```

---

### Advanced Concept 2: PairGrid for Total Control of Pair Plots

`PairGrid` is the lower-level version of `pairplot` — full control over upper, lower, and diagonal:

```python
penguins = sns.load_dataset("penguins").dropna()
PALETTE  = {"Adelie": "#E74C3C", "Chinstrap": "#3498DB", "Gentoo": "#2ECC71"}

g = sns.PairGrid(penguins,
                 vars=["bill_length_mm", "bill_depth_mm",
                        "flipper_length_mm", "body_mass_g"],
                 hue="species", palette=PALETTE,
                 corner=True)

# Upper triangle: scatter
g.map_upper(sns.scatterplot, alpha=0.4, s=20)

# Diagonal: KDE
g.map_diag(sns.kdeplot, fill=True, alpha=0.4, linewidth=1.5)

# Lower triangle: KDE contour (2D)
g.map_lower(sns.kdeplot, fill=True, alpha=0.3, thresh=0.05, levels=5)

g.add_legend(title="Species", adjust_subtitles=True)
g.figure.suptitle("PairGrid — Penguin Species", y=1.01, fontsize=14, fontweight="bold")
plt.savefig("pairgrid_advanced.png", dpi=150, bbox_inches="tight")
plt.show()
```

---

### Advanced Concept 3: Seaborn + Matplotlib Hybrid for Complex Layouts

Seaborn figure-level plots create their own figures, but you can embed axes-level Seaborn plots into complex Matplotlib GridSpec layouts:

```python
import matplotlib.gridspec as gridspec
import seaborn as sns
import matplotlib.pyplot as plt
import numpy as np

sns.set_theme(style="darkgrid")
tips    = sns.load_dataset("tips")
penguins = sns.load_dataset("penguins").dropna()

fig = plt.figure(figsize=(16, 10))
gs  = gridspec.GridSpec(2, 3, figure=fig, hspace=0.4, wspace=0.35)

ax1 = fig.add_subplot(gs[0, :2])   # top-left wide: spanning 2 columns
ax2 = fig.add_subplot(gs[0, 2])    # top-right: single column
ax3 = fig.add_subplot(gs[1, 0])    # bottom left
ax4 = fig.add_subplot(gs[1, 1])    # bottom middle
ax5 = fig.add_subplot(gs[1, 2])    # bottom right

# Plot on each axes using axes-level Seaborn
sns.lineplot(data=tips, x="total_bill", y="tip", hue="time", ax=ax1)
ax1.set_title("Tip vs Bill by Time")

sns.countplot(data=tips, x="day", hue="sex", ax=ax2, palette="pastel")
ax2.set_title("Count by Day")

sns.boxplot(data=penguins, x="species", y="body_mass_g",
            palette="Set2", ax=ax3)
ax3.set_title("Body Mass by Species")

sns.kdeplot(data=penguins, x="flipper_length_mm",
            hue="species", fill=True, alpha=0.4, ax=ax4)
ax4.set_title("Flipper Length KDE")

corr = penguins.select_dtypes("number").corr()
sns.heatmap(corr, annot=True, fmt=".2f", cmap="coolwarm",
            center=0, linewidths=0.5, ax=ax5, cbar=False)
ax5.set_title("Correlation")

fig.suptitle("Multi-Dataset Analysis Dashboard",
             fontsize=16, fontweight="bold", y=1.01)
plt.savefig("hybrid_dashboard.png", dpi=150, bbox_inches="tight")
plt.show()
```

---

### Advanced Concept 4: Reproducing Publication Figures

Academic journals require specific aesthetics. Here's how to match Nature/Science style:

```python
import seaborn as sns
import matplotlib.pyplot as plt
import matplotlib as mpl

# Publication style settings
sns.set_theme(style="ticks", context="paper")
mpl.rcParams.update({
    "font.family":      "serif",
    "font.size":        9,
    "axes.linewidth":   0.8,
    "xtick.major.width": 0.8,
    "ytick.major.width": 0.8,
    "lines.linewidth":  1.2,
    "figure.dpi":       300,
    "savefig.dpi":      300,
})

tips = sns.load_dataset("tips")

fig, axes = plt.subplots(1, 2, figsize=(6.5, 2.8))  # two-column figure width

# Panel A
ax = axes[0]
sns.scatterplot(data=tips, x="total_bill", y="tip",
                hue="time", palette=["#2166AC", "#D6604D"],
                s=20, alpha=0.7, linewidth=0, ax=ax)
sns.regplot(data=tips, x="total_bill", y="tip",
            scatter=False, color="black", line_kws={"lw": 1}, ax=ax)
ax.set_xlabel("Total bill (USD)")
ax.set_ylabel("Tip (USD)")
ax.set_title("A", loc="left", fontweight="bold")
sns.despine(ax=ax, trim=True)

# Panel B
ax2 = axes[1]
sns.violinplot(data=tips, x="day", y="total_bill",
               order=["Thur", "Fri", "Sat", "Sun"],
               palette="muted", inner="quartile",
               linewidth=0.8, ax=ax2)
ax2.set_xlabel("Day")
ax2.set_ylabel("Total bill (USD)")
ax2.set_title("B", loc="left", fontweight="bold")
sns.despine(ax=ax2, trim=True)

plt.tight_layout(pad=1.2)
plt.savefig("publication_figure.pdf", bbox_inches="tight")  # PDF = vector = print-ready
plt.savefig("publication_figure.png", dpi=300, bbox_inches="tight")
plt.show()
```

---

### ⚡ Performance & Optimization

| Optimization Technique               | Impact | When to Use                                           |
|--------------------------------------|--------|-------------------------------------------------------|
| `.dropna()` before plotting          | High   | Any plot type — prevents silent errors                |
| `corner=True` in pairplot            | High   | Large datasets — reduces half the computations        |
| `kind="hist"` instead of `"kde"` in displot | Medium | Very large datasets (KDE is slow on 100k+ rows) |
| Sample before pairplot               | High   | Datasets > 10k rows — `df.sample(2000)` first        |
| `bw_adjust` in kdeplot               | Medium | Tune bandwidth instead of recomputing from scratch    |
| `rasterized=True` in scatterplot     | Medium | Scatter plots in PDF/SVG with 10k+ points            |
| Use `catplot` with `sharex/sharey`   | Low    | Avoids redundant axis rendering in faceted grids      |
| `sns.set(font_scale=...)` globally   | Low    | Faster than setting fontsize in every call            |

```python
# Downsampling for performance
import seaborn as sns
import pandas as pd

diamonds = sns.load_dataset("diamonds")  # 53940 rows

# ❌ Slow: pairplot on 54k rows
# sns.pairplot(diamonds, hue="cut")

# ✅ Fast: sample 3000 rows
sample = diamonds.sample(3000, random_state=42)
sns.pairplot(sample, hue="cut", vars=["carat", "price", "depth"])
plt.show()
```

---

## 🗺️ 10. Complete Roadmap

> 🎯 *Goal: Know exactly what to learn and in what order.*

---

### 📅 Week-by-Week Learning Path

```
PHASE 1 — FOUNDATION (Week 1–2)
├── Day 1–2:   Install Seaborn, sns.set_theme(), load_dataset()
│              scatterplot, lineplot — the data= / x= / y= / hue= pattern
├── Day 3–4:   histplot, kdeplot — understanding distributions
│              barplot vs countplot — when to use each
├── Day 5–6:   boxplot, violinplot — categorical comparisons
│              Color palettes: qualitative vs sequential vs diverging
└── Day 7–8:   sns.despine(), plt.tight_layout(), plt.savefig()
               🏗 PROJECT: Titanic Survival Explorer (beginner project above)

PHASE 2 — CORE SKILLS (Week 3–4)
├── Day 9–10:  heatmap — correlation matrices for ML EDA
│              Masking upper triangle, annotations, cmap choices
├── Day 11–12: pairplot — multivariate overview in one line
│              jointplot — bivariate + marginal distributions
└── Day 13–14: Combining Seaborn with Matplotlib (ax return value)
│              overlay multiple plot types on same axes
               🏗 PROJECT: Penguins Full EDA Dashboard (intermediate project)

PHASE 3 — INTERMEDIATE (Week 5–6)
├── Week 5:    FacetGrid — col/row faceting across categories
│              relplot, displot, catplot — figure-level functions
│              lmplot, regplot — regression visualization
└── Week 6:    Customizing figure-level plots via .figure / .fig
│              Combining Seaborn + Matplotlib GridSpec
│              Custom color palettes, per-figure styling
               🏗 PROJECT: Multi-Dataset Analysis Dashboard

PHASE 4 — ADVANCED (Week 7–8)
├── Week 7:    PairGrid — full control of diagonal/upper/lower mappings
│              Custom FacetGrid.map_dataframe() with user functions
│              statannotations — p-value annotations
└── Week 8:    Publication-quality figures (paper context, serif fonts, PDF)
│              Performance optimization for large datasets
│              clustermap — hierarchical clustering + heatmap
               🏗 PROJECT: ML Feature Analysis Dashboard (advanced project)

PHASE 5 — MASTERY (Month 3+)
├── Build a reusable EDA function library (your personal seaborn toolkit)
├── Explore Plotly for interactive equivalents of Seaborn plots
├── Study visual design principles (Edward Tufte's data-ink ratio)
├── Contribute EDA notebooks to Kaggle competitions
└── Build a professional data analysis portfolio with Seaborn figures
```

---

### 🏁 Milestone Checklist

- [ ] I can install Seaborn and set a theme before every project
- [ ] I understand the `data=df, x="col", y="col", hue="col"` pattern
- [ ] I know when to use: scatter, line, bar, count, box, violin, hist, kde
- [ ] I can produce a correlation heatmap with annotations and masking
- [ ] I can create a `pairplot` and `jointplot` for EDA
- [ ] I know the difference between axes-level and figure-level functions
- [ ] I can use `FacetGrid` for faceted multi-panel plots
- [ ] I can combine Seaborn with Matplotlib for fine-tuning
- [ ] I have built at least one real EDA project using a real dataset
- [ ] I can save publication-quality PNG/PDF figures (dpi=300)

---

## 🧩 11. Bonus Deep Insights

> 🎯 *Things most people spend years figuring out — here upfront.*

---

### 🔮 Mental Model: Seaborn as a Statistical Translator

The most powerful way to think about Seaborn: it's a **translator between your statistical questions and visual answers**.

Every Seaborn function is the answer to a specific question:

```
"How is X distributed?"         → histplot / kdeplot
"How does X differ across groups?"  → boxplot / violinplot / barplot
"How do X and Y relate?"        → scatterplot / regplot / jointplot
"How do all variables relate?"  → pairplot / heatmap
"How does X behave across two categorical factors?" → catplot with col= and row=
```

When you're stuck, don't think "which plot should I use?" — instead ask "what question am I trying to answer?" Then the right Seaborn function follows naturally.

---

### 🤫 Secret 1: `sns.barplot()` Computes Statistics — It's Not a Bar Counter

This is the single biggest confusion in Seaborn. `barplot` doesn't count things — it computes the **mean** of your `y` column and draws **95% confidence intervals** automatically.

```python
tips = sns.load_dataset("tips")

# This shows MEAN tip per day + CI:
sns.barplot(data=tips, x="day", y="tip")
# y="tip" → compute mean(tip) per day, add CI bars

# This shows COUNT per day (no y needed):
sns.countplot(data=tips, x="day")
```

This is not a bug — it's a feature. `barplot` is designed for statistical comparisons. The CI bands show whether group means are significantly different. That's what makes Seaborn a *statistical* visualization library.

---

### 🤫 Secret 2: `lineplot()` is a Statistical Aggregator Too

When multiple y-values exist at the same x, `lineplot` automatically computes their **mean** and draws a **confidence interval band**:

```python
fmri = sns.load_dataset("fmri")
print(fmri.groupby("timepoint")["signal"].count())
# Multiple rows per timepoint!

# This draws ONE line (mean per timepoint) + CI band:
sns.lineplot(data=fmri, x="timepoint", y="signal")

# This draws raw data — ALL lines visible:
for subject in fmri["subject"].unique():
    sub_data = fmri[fmri.subject == subject]
    plt.plot(sub_data["timepoint"], sub_data["signal"], alpha=0.2, color="gray")
sns.lineplot(data=fmri, x="timepoint", y="signal", color="blue", lw=3)  # mean on top
```

---

### 🤫 Secret 3: Seaborn is Built on Matplotlib — Full Access at Any Time

Seaborn doesn't replace Matplotlib. It *wraps* it. This means:
- Every Seaborn axes-level function returns a Matplotlib `Axes` — use all of Matplotlib's methods on it.
- Every Seaborn figure-level function has a `.figure` attribute (or `.fig` for PairGrid/JointGrid) — a real Matplotlib `Figure`.
- You can mix `sns.*` and `ax.*` / `plt.*` calls freely.

```python
fig, ax = plt.subplots(figsize=(9, 5))

sns.kdeplot(data=tips, x="total_bill", hue="time",
            fill=True, alpha=0.4, ax=ax)

# Now use raw Matplotlib on the same axes:
ax.axvline(tips["total_bill"].median(), color="black", lw=2, ls="--")
ax.text(tips["total_bill"].median() + 0.5, 0.035,
        f"Median: ${tips['total_bill'].median():.1f}",
        fontsize=10, color="black")
ax.set_xlim(0, 60)
ax.spines["top"].set_visible(False)
ax.spines["right"].set_visible(False)
plt.title("Bill Distribution with Median Marker")
plt.show()
```

---

### 🤫 Secret 4: `clustermap` is the Most Underused Power Tool

Most beginners use `heatmap` and never discover `clustermap`. But `clustermap` does something fundamental that `heatmap` can't: it **reorders the rows and columns** using hierarchical clustering, so that similar features/samples are grouped together.

This is invaluable for:
- **Correlation matrices**: grouped features reveal which features are redundant
- **Gene expression data**: samples with similar profiles cluster together
- **User behavior matrices**: users with similar patterns group automatically

```python
# With heatmap: fixed order (often arbitrary / alphabetical)
sns.heatmap(corr)

# With clustermap: OPTIMAL order based on similarity
sns.clustermap(corr, cmap="coolwarm", center=0, annot=True, fmt=".2f",
               method="ward", metric="euclidean",
               figsize=(10, 10))
# The dendrogram on the left/top shows which features are most similar
```

---

### 🧠 The Big Picture

Seaborn occupies a precise niche in the Python visualization ecosystem:

```
Raw Data (CSV, DB, API)
      ↓
Pandas (cleaning, transformation, feature engineering)
      ↓
  SEABORN ← statistical visualization of DataFrames
      ↑            ↑
Matplotlib    (underlying rendering engine)
      ↓
  Output Layer:
  ├── Static figures → PNG / PDF / SVG (for reports, papers)
  ├── Notebook inline → Jupyter / Google Colab
  └── Interactive → Plotly (different library)
```

**What comes before it:** Python basics, Pandas DataFrames, basic statistics (mean, median, distribution, correlation).
**What it enables:** Fast, rigorous EDA; ML feature analysis; publication figures; data storytelling.
**Where it's going:** Seaborn v0.13+ introduced a major API refinement with the new `so` (seaborn.objects) interface — a fully declarative, grammar-of-graphics-style API. It's the future of Seaborn and worth exploring after mastering the classic interface.

```python
# Preview: The new seaborn.objects interface (modern, declarative)
import seaborn.objects as so

(
    so.Plot(tips, x="total_bill", y="tip", color="time")
    .add(so.Dot(alpha=0.5))
    .add(so.Line(), so.PolyFit())
    .facet(col="sex")
    .label(title="Tips Analysis")
    .show()
)
```

---

## 📌 12. Summary (Quick Revision)

> 🎯 *Everything important — at a glance.*

---

### Core Concepts (1-line each)

| Concept               | What It Means                                                                  |
|-----------------------|--------------------------------------------------------------------------------|
| `sns.set_theme()`     | Globally sets style, context, palette — call ONCE at the top                  |
| `data=df, x=, y=`     | Seaborn's universal input pattern — always use DataFrame + column names        |
| `hue=`                | Splits data by a column's values — colors each group + auto-adds legend        |
| `style=`              | Splits data by a column — varies marker shape or linestyle                     |
| `size=`               | Splits data by a column — varies point/line size                               |
| Axes-level functions  | `scatterplot`, `boxplot`, `histplot`, etc. — return Matplotlib `Axes`          |
| Figure-level functions| `relplot`, `catplot`, `displot`, `lmplot` — return FacetGrid; own figure       |
| `barplot()`           | Shows MEAN + CI per category — NOT a counter (use `countplot` for counts)      |
| `lineplot()`          | Auto-aggregates to mean + CI band when multiple y per x                        |
| `heatmap()`           | Color-encodes a 2D matrix; key for correlation matrices in ML                  |
| `pairplot()`          | Auto-creates scatter matrix of all numeric variable pairs                      |
| `FacetGrid`           | Manually tile any plot across a grid of category values                        |
| `clustermap()`        | Heatmap + hierarchical clustering — reorders rows/cols by similarity           |
| `sns.despine()`       | Removes top/right spines — instant modern, clean look                          |

---

### The 5 Things to Remember

1. ✅ **Always call `sns.set_theme()` first** — before any plot, every time. It's not optional if you want consistent, beautiful results.
2. ✅ **Use `data=df, x="col"` — never pass arrays** — Seaborn's power comes from understanding DataFrame structure; passing arrays bypasses all of that.
3. ✅ **Know axes-level vs figure-level** — figure-level (`relplot`, `catplot`, `displot`, `pairplot`, etc.) create their own Figure; axes-level accept `ax=` parameter.
4. ✅ **`barplot` = mean + CI, `countplot` = frequencies** — confusing these two is the #1 Seaborn mistake.
5. ✅ **Seaborn is a Matplotlib wrapper** — the `ax` or `fig` returned by any Seaborn function gives you full Matplotlib access for fine-tuning.

---

### Quick Reference Cheat Sheet

```python
# ─── SETUP ───────────────────────────────────────────────────────────────
import seaborn as sns
import matplotlib.pyplot as plt
import pandas as pd
import numpy as np

sns.set_theme(style="whitegrid", context="notebook", palette="deep")
# styles:   "darkgrid" | "whitegrid" | "white" | "dark" | "ticks"
# contexts: "paper" | "notebook" | "talk" | "poster"

# ─── LOAD DATA ───────────────────────────────────────────────────────────
df = sns.load_dataset("tips")        # built-in
df = pd.read_csv("mydata.csv")       # from file

# ─── RELATIONAL PLOTS ────────────────────────────────────────────────────
sns.scatterplot(data=df, x="col1", y="col2", hue="cat", style="cat2")
sns.lineplot(data=df, x="col1", y="col2", hue="cat")  # auto mean+CI
sns.relplot(data=df, x="col1", y="col2", col="cat", row="cat2", kind="scatter")

# ─── DISTRIBUTION PLOTS ──────────────────────────────────────────────────
sns.histplot(data=df, x="col", hue="cat", bins=30, kde=True, stat="density")
sns.kdeplot(data=df, x="col", hue="cat", fill=True, alpha=0.4)
sns.ecdfplot(data=df, x="col", hue="cat")
sns.displot(data=df, x="col", col="cat", kind="kde", fill=True)

# ─── CATEGORICAL PLOTS ───────────────────────────────────────────────────
sns.barplot(data=df, x="cat", y="num", hue="cat2", capsize=0.1)  # mean+CI
sns.countplot(data=df, x="cat", hue="cat2")                       # counts
sns.boxplot(data=df, x="cat", y="num", hue="cat2")
sns.violinplot(data=df, x="cat", y="num", hue="cat2", split=True)
sns.stripplot(data=df, x="cat", y="num", jitter=True, alpha=0.5)
sns.swarmplot(data=df, x="cat", y="num", size=4)
sns.catplot(data=df, x="cat", y="num", col="cat2", kind="violin")

# ─── REGRESSION PLOTS ────────────────────────────────────────────────────
sns.regplot(data=df, x="col1", y="col2", ci=95)
sns.lmplot(data=df, x="col1", y="col2", hue="cat", col="cat2")

# ─── MATRIX PLOTS ────────────────────────────────────────────────────────
corr = df.select_dtypes("number").corr()
mask = np.triu(np.ones_like(corr, dtype=bool))
sns.heatmap(corr, mask=mask, annot=True, fmt=".2f", cmap="coolwarm",
            center=0, square=True, vmin=-1, vmax=1)
sns.clustermap(corr, annot=True, fmt=".2f", cmap="coolwarm", center=0)

# ─── MULTI-PLOT GRIDS ────────────────────────────────────────────────────
sns.pairplot(df, hue="cat", vars=["col1","col2","col3"], corner=True)
sns.jointplot(data=df, x="col1", y="col2", hue="cat", kind="scatter")
g = sns.FacetGrid(df, col="cat", row="cat2")
g.map_dataframe(sns.scatterplot, x="col1", y="col2")

# ─── STYLE UTILITIES ─────────────────────────────────────────────────────
sns.despine()                                    # remove top/right spines
sns.despine(left=True, trim=True)                # more aggressive
ax.set_title("Title", fontsize=13, fontweight="bold")  # via returned ax
g.fig.suptitle("Overall Title", y=1.01)                # figure-level

# ─── OUTPUT ──────────────────────────────────────────────────────────────
plt.tight_layout()
plt.savefig("fig.png", dpi=300, bbox_inches="tight")
plt.savefig("fig.pdf", bbox_inches="tight")  # vector PDF
plt.show()
plt.close()  # free memory in loops
```

---

### What's Next?

After mastering Seaborn, consider exploring:

- 📘 **Plotly / Plotly Express** — Interactive, zoomable versions of everything Seaborn does. `px.scatter()`, `px.box()`, `px.imshow()` mirror Seaborn's API but output interactive HTML charts. Natural upgrade for dashboards and web.
- 📘 **Seaborn Objects API (`seaborn.objects`)** — The new declarative, grammar-of-graphics interface in Seaborn 0.12+. The future of the library — more flexible and composable than the classic API.
- 📘 **Altair** — Pure declarative visualization using Vega-Lite specification. Excellent for complex linked/interactive charts without JavaScript.
- 📘 **Bokeh** — Python-native interactive visualization for web browsers. Good for building standalone data apps.
- 📘 **Edward Tufte's "The Visual Display of Quantitative Information"** — The foundational book on data visualization design. Will transform how you think about every chart you make.

---

> 💬 *"The greatest value of a picture is when it forces us to notice what we never expected to see."*
> — John W. Tukey, statistician and father of exploratory data analysis

---

*Guide generated with the MD Masterpiece Generator skill.*
*Topic: Python Seaborn | Version: 1.0 | Built for: Deb Barman — AI Developer & Class XI Student*
