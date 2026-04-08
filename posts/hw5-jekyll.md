---
layout: post
title: "IS445: Homework 5"
author: "Aaliyah Ali"
---

## Homework 5

<div style="display:flex; justify-content:space-between; flex-wrap:wrap; gap:10px; margin:20px 0;">
  <a style="padding:10px 16px; border:1px solid #0d6efd; color:#0d6efd; text-decoration:none; border-radius:6px;"
     href="https://raw.githubusercontent.com/UIUC-iSchool-DataViz/is445_data/main/licenses_fall2022.csv">
    The Data
  </a>

  <a style="padding:10px 16px; border:1px solid #0d6efd; color:#0d6efd; text-decoration:none; border-radius:6px;"
     href="https://github.com/aaliyahali/aaliyahali/blob/main/licenses-homework.ipynb">
    The Analysis
  </a>
</div>

---

## Chart 1: Top 20 Illinois Professional License Types

<div id="plot1"></div>

**What is being visualized:**  
This horizontal bar chart displays the 20 most common professional license types issued in Illinois, ranked from most to least frequent.

**Design choices – encodings:**  
The x-axis represents license counts (quantitative), and the y-axis represents license type (nominal), sorted descending.

**Design choices – colormap:**  
Uses `tealblues` sequential color scheme to reinforce magnitude.

**Data transformations:**  
Used `value_counts()` on `License Type` and selected top 20.

**Interactivity:**  
Click to highlight bars + tooltip on hover.

---

## Chart 2: License Status Breakdown for Top 10 License Types

<div id="plot2"></div>

**What is being visualized:**  
Normalized stacked bar chart showing proportions of license statuses across top 10 license types.

**Design choices – encodings:**  
- x-axis: percentage (normalized)  
- y-axis: license type  
- color: license status  

**Design choices – colormap:**  
Uses `tableau10` categorical scheme.

**Data transformations:**  
Grouped by `License Type` and `License Status`, filtered to top categories.

**Interactivity:**  
Hover shows raw counts behind proportions.

---

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#plot1', 'plot1.json');
  vegaEmbed('#plot2', 'plot2.json');
</script>
