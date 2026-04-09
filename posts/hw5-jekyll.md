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

This plot depicts the top 20 professional licenses in the state of Illinois, listed in descending order. Each bar represents one license category, and the bar length represents the total count of licenses held in that category. This visualization this hopes to provide a quick overview of which professional licenses are most prominent in the state. 

In terms of encodying types, the x-axis ses a quantitative encoding to represent the count of licenses, and the y-axis uses a nominal encoding for license type. The bars in the plot are colored using the tealblues sequential color scheme, which is mapped directly to the count value. This scheme progresses from light to dark teal, which hopes to represent the magnitude already encoded in bar length: darker bars are more common license types, while lighter bars are less frequenct. 

In terms of data transformation, I used aggregated the License Type column to save per-type totals, then filtered the result to the top 20 entries.

For interactivity, this chart uses a point selection (selection_point) -- if a user clicks on any bar, it highlights it in the teal color scheme while all other bars dim to gray. This interaction is useful to help a user focus on a specific license type, which can be especially  useful when comparing a particular bar against others in this ranking. 

---

## Chart 2: License Status Breakdown for Top 10 License Types

<div id="plot2"></div>

This stacked bar chart plot depicts the top 10 most popular professional licenses in the state of IL, which are further broken down by their status type. Rather than showing raw counts, the data was normalized so that each bar is scaled to 100% so the viewer can directly compare the composition of statuses across very different-sized professions. 

In terms of encoding, the y-axis uses a nominal encoding for license type, and and the x-axis uses a quantitative encoding which is displayed as a normalized percentage. Color is used to encode the license status category using a nominal mapping. The stack='normalize' option in Altair transforms the bars so all extend to 100%, which shifts the focus from total volume to proportional composition, which aims to support the user in quickly being able to compare license status breakdowns across different licenses. 

For coloing, the tableau10 categorical color scheme is used to differentiate the license statuses. Since status is a nominal variable with no inherent ordering, a categorical scheme would be most applicable. Also, tableau10 provides up to 10 visually distinct colors. In this plot, though, only the top 5 license statuses by total count are retained to prevent the legend from becoming overfilled and cramped with more rare categories.

In terms of data transformation, I first filtered the dataframe to keep only the observations whose License Type is in the top 10 list (derived from Plot 1). I then used the groupby function to count the combinations of License Type and License status; then, I further filtered to keep only the 5 most common status values (summed across all license types). This filtering was key to keep the chart readable and clean, as the raw data had quite a few rare license statuses, which would simply dilute the bar charts and create a less insightful visualization. 



---

<script src="https://cdn.jsdelivr.net/npm/vega@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-lite@5"></script>
<script src="https://cdn.jsdelivr.net/npm/vega-embed@6"></script>

<script>
  vegaEmbed('#plot1', '/plot1.json');
  vegaEmbed('#plot2', '/plot2.json');
</script>
