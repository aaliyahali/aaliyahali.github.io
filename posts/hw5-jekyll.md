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
     href="https://github.com/aaliyahali/aaliyahali.github.io/blob/95bacf18e66a14654f085d4a6c0370e8f096813d/licenses-homework.ipynb">
    The Analysis
  </a>
</div>

---

## Chart 1: Top 20 Illinois Professional License Types

<div id="plot1"></div>

Description of plot

---

## Chart 2: License Status Breakdown for Top 10 License Types

<div id="plot2"></div>

description of plot

---

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#plot1', '/plot1.json');
  vegaEmbed('#plot2', '/plot2.json');
</script>
