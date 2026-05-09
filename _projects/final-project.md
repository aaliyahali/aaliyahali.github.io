---
name: Race and Representation in Clinical Drug Trials
tools: [Python, Altair, Jekyll]
image: assets/pngs/cancer_trials.png
description: An interactive data journalism article examining racial and demographic disparities in FDA clinical drug trial participation from 2015 to 2018.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Race and Representation in Clinical Drug Trials

**Authors: Aaliyah Ali, Roqaya Elmenshawy, Livia Lin, Noor Esily**

---

## FDA: Development of New Drugs and Clinical Trials 

When the U.S. Food and Drug Administration (FDA) approves a new drug, it is making a guarantee to the public, which states that this medicine is safe and effective. However, the important caveat here lies in who exactly the drug was intedned to be safe and effective for. Drug approvals stem from the data collected from clinical trials, which are carefully monitored studies where real patients take an experimental drug and researchers measure the results. Thus, if the patients in the trial do not represent the general population who may actually take those drugs, then perhaps the results of these trals may not apply equally to everyone.

Between January 2015 and mid-August 2018, the FDA approved 155 new drugs and compiled demographic snapshots for each, which included a recording of what percentage of trial participants were White, Black, Asian, women, or over the age of 65. ProPublica, which is an investigative news organization, compiled all of this information into a single dataset and for the purpose of investigating racial representation in drug trials. Our analysis builds upon that premise to look at all disease categories in order to highlight systemic underreprsentation across racial demographic factors. 

---

## The Interactive Dashboard

The dashboard below lets you explore the full picture of the data yourself. You can use the **dropdown menu** to switch between demographic groups — Black participants, White participants, Asian participants, Women, and patients aged 65 and older. The **top bar chart** shows the average participation rate for the selected demographic broken down by disease category. **Click any bar** to filter the histogram below and see how individual drugs within that category are distributed. **Double-click** to reset back to all categories.

<vegachart schema-url="{{ site.baseurl }}/interactive-dashboard.json" style="width: 100%"></vegachart>

A few patterns worth exploring:

- Select **Black / African American** and click **Infectious Disease** — participation jumps to ~21%, the highest of any category, largely driven by HIV and Hepatitis C trials that actively recruit from communities with higher disease prevalence.
- Stay on **Black / African American** and click **Cancer** — participation drops to ~3%, and the histogram shows most drugs clustered near zero. This is the most alarming finding in the entire dataset.
- Switch to **Cardiovascular** — Black participation falls to ~3.6% despite the fact that Black Americans face disproportionately high rates of heart disease and hypertension.
- Switch to **Women** — participation is above 50% in Cancer trials largely because breast, ovarian, and cervical cancer trials enroll only women. Neurological and Cardiovascular trials fall below the parity line.

---

## Cancer Trials: A Key Gap

Of all the disparities across trials in this dataset, the one in cancer drug trials is quite large. The chart below compares cancer incidence rates by race over the same 2015–2018 window using data from the National Cancer Institute's SEER program. Black Americans have the highest cancer incidence rate of any group, but  they are nearly absent from the trials used to prove that these very cancer drugs work.

<vegachart schema-url="{{ site.baseurl }}/contextviz1.json" style="width: 100%"></vegachart>

*Source: National Cancer Institute, SEER Cancer Statistics Explorer. [seer.cancer.gov](https://seer.cancer.gov/statistics-network/explorer/)*

This chart shows cancer incidence rates per 100,000 people by race from 2015 to 2018. Black Americans consistently have the highest rates — higher than White, Asian, or Hispanic Americans — yet as we saw in the dashboard, they make up only about 3% of cancer drug trial participants. The disconnect between who bears the greatest disease burden and who is represented in the research meant to address it is stark and consequential.

When normalized to compare directly against trial participation, the gap becomes even clearer. The chart below compares each group's share of U.S. cancer cases against their share of cancer drug trial participants. Black Americans account for roughly 37% of cancer cases among these three racial groups but only about 3% of cancer trial participants — an over ten-fold disproportion.

<vegachart schema-url="{{ site.baseurl }}/contextviz2.json" style="width: 100%"></vegachart>

*Source: NCI SEER 2015–2018 (cancer incidence); ProPublica/FDA Drug Trials Snapshots (trial participation).*

---

## Deeper Dive: Black Participant Representation Across Cancer Trials

The dot plot below shows every individual FDA-approved cancer drug from this period, sorted by the percentage of Black participants in its trial. Each dot is one drug. The clustering near zero indicates that the vast majority of cancer drugs were approved on the basis of trials where Black patients represented less than 5% of participants. Additionally, several drugs were approved with effectively zero Black participants recorded.

<vegachart schema-url="{{ site.baseurl }}/extracredit1.json" style="width: 100%"></vegachart>

---

## The Importance Of This Analysis

add a conclusion paragraph here - roqaya 
---

## Data Sources & Citations

- **Primary dataset:** ProPublica, *Clinical Trials: Participant Demographic Data* (2018). Compiled from FDA Drug Trials Snapshots, January 2015 – August 2018.
  [https://projects.propublica.org/datastore/#cancer-clinical-trials-demographics-data](https://projects.propublica.org/datastore/#cancer-clinical-trials-demographics-data)
  License: ProPublica Standard Terms of Use.

- **Cancer incidence by race:** National Cancer Institute, Surveillance, Epidemiology, and End Results (SEER) Program, Cancer Statistics Explorer, 2022.
  [https://seer.cancer.gov/statistics-network/explorer/](https://seer.cancer.gov/statistics-network/explorer/)

- **U.S. population by race:** U.S. Census Bureau, 2020 Decennial Census, Table P2.
  [https://data.census.gov/table/DECENNIALPL2020.P2](https://data.census.gov/table/DECENNIALPL2020.P2)

- **Original reporting:** Duehren, A., & Ornstein, C. (2018). *Black Patients Miss Out on Promising Cancer Drugs.* ProPublica.
  [https://www.propublica.org/article/black-patients-miss-out-on-promising-cancer-drugs](https://www.propublica.org/article/black-patients-miss-out-on-promising-cancer-drugs)

---

## Analysis Notebooks & Data

<div style="display: flex; gap: 1rem; flex-wrap: wrap; margin-top: 0.5rem;">
  <a href="https://github.com/aaliyahali/aaliyahali.github.io/blob/main/01_data_cleaning.ipynb" class="btn btn-outline-dark">
    Data Cleaning Notebook
  </a>
  <a href="https://github.com/aaliyahali/aaliyahali.github.io/blob/main/fp-part3.ipynb" class="btn btn-outline-dark">
    Analysis & Visualization Notebook
  </a>
  <a href="https://raw.githubusercontent.com/aaliyahali/aaliyahali.github.io/main/
    Cleaned Dataset (CSV)
  </a>
</div>