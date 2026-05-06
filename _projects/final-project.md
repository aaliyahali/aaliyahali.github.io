---
name: Race and Representation in Clinical Drug Trials
tools: [Python, Altair, Jekyll]
image: assets/pngs/contextual1.png
description: An interactive data journalism article examining racial and demographic disparities in FDA clinical drug trial participation (2015–2018).
---

# Race and Representation in Clinical Drug Trials

**Authors: Aaliyah Ali, Roqaya Elmenshawy, Livia Lin, Noor Esily**

---

## Introduction

When the U.S. Food and Drug Administration (FDA) approves a new drug, it is making a guarantee to the public: this medicine is safe and effective. But safe and effective *for whom*? Every drug approval is based on data collected from clinical trials — carefully controlled studies where real patients take an experimental drug and researchers measure the results. If the patients enrolled in those trials do not reflect the diversity of the people who will eventually take the drug, the results may not apply equally to everyone.

Between January 2015 and mid-August 2018, the FDA approved 155 new drugs and compiled demographic snapshots for each one — recording what percentage of trial participants were White, Black, Asian, women, or over the age of 65. ProPublica, an investigative news organization, compiled all of these snapshots into a single dataset and used it to investigate racial representation in cancer drug trials. Our analysis expands that investigation to cover all disease categories, from infectious disease to cardiovascular conditions, revealing a systematic pattern of underrepresentation that varies dramatically depending on which disease the drug is treating.

## The Big Picture: Who Is Actually in Clinical Trials?

Across all 155 drugs approved in this period, the average trial participant was overwhelmingly White — about 75.6% of participants on average — while Black participants made up only 8.3% and Asian participants 9.7%. To put that in context, Black Americans make up approximately 12.4% of the U.S. population according to the 2020 Census, meaning they are underrepresented even compared to their share of the general population. But the picture gets significantly worse when you look at specific disease categories.

The chart below compares each racial group's share of the U.S. population against their average share of clinical trial participants across all 155 approved drugs. White patients are consistently overrepresented, while Black patients are notably underrepresented.

<vegachart schema-url="{{ site.baseurl }}/contextual2.json" style="width: 100%"></vegachart>

*Source: U.S. Census Bureau 2020 Decennial Census (population shares); ProPublica/FDA Drug Trials Snapshots (trial participation). [Census data](https://data.census.gov/table/DECENNIALPL2020.P2)*

## The Cancer Problem

The disparity is sharpest in cancer drug trials. Black Americans represent approximately 13.2% of U.S. cancer diagnoses — but only **3%** of cancer drug trial participants on average. That means that for every 100 people enrolled in a cancer drug trial, fewer than 3 are Black, even though more than 13 out of every 100 Americans diagnosed with cancer are Black. This gap matters because cancer treatments can have different effectiveness and side effect profiles depending on a patient's genetic background, and if Black patients are nearly absent from the trials used to approve those drugs, we simply do not know how well those drugs will work for them.

The chart below makes this gap visible directly. The blue bars show each group's actual share of U.S. cancer diagnoses; the red bars show their share of cancer drug trial participants. The gap for Black Americans is stark.

<vegachart schema-url="{{ site.baseurl }}/contextual1.json" style="width: 100%"></vegachart>

*Source: National Cancer Institute SEER Cancer Statistics 2022 (cancer incidence by race); ProPublica/FDA Drug Trials Snapshots (trial participation). [NCI SEER data](https://seer.cancer.gov/statistics-network/explorer/)*

## Explore the Data Yourself

The dashboard below lets you examine the full picture interactively. Use the **dropdown menu** to switch between different demographic groups — Black participants, White participants, Asian participants, Women, and patients aged 65 and older. The top bar chart shows the average participation rate for the selected demographic broken down by disease category. **Click any bar** to filter the histogram below to show the distribution of individual drugs within that category. **Double-click** to reset and show all drugs at once.

<vegachart schema-url="{{ site.baseurl }}/interactive-dashboard.json" style="width: 100%"></vegachart>

*Data source: ProPublica Clinical Trials Demographics Dataset, compiled from FDA Drug Trials Snapshots (January 2015 – August 2018). [Download dataset](https://projects.propublica.org/datastore/#cancer-clinical-trials-demographics-data)*

A few patterns worth exploring in the dashboard:

- Switch to **Infectious Disease** — Black participation jumps to ~21.8%, the highest of any category, likely driven by HIV and Hepatitis C trials that actively recruit from higher-prevalence communities.
- Switch to **Cardiovascular** — Black participation drops to ~3.6%, despite Black Americans facing disproportionately high rates of heart disease and hypertension.
- Switch to **Women** — Cancer trials are above the 50% mark largely because breast, ovarian, and cervical cancer trials are women-only. Neurological and Cardiovascular trials fall below parity.

## Not Getting Better Fast Enough

One might hope that these disparities are a historical artifact and that trials have become more diverse over time. The trend line below shows the average Black participation rate across disease categories from 2015 to 2018. While there is a modest upward trend overall — from 7.6% in 2015 to 11.8% in 2018 — the increase is driven largely by Infectious Disease trials. Cancer trials remain stubbornly near the bottom throughout the entire period.

<vegachart schema-url="{{ site.baseurl }}/extracredit2.json" style="width: 100%"></vegachart>

## A Drug-by-Drug Look at Cancer

The dot plot below shows every individual FDA-approved cancer drug from this period, plotted by the percentage of Black participants in its trial. Each dot is one drug. The clustering near zero is unmistakable — the vast majority of cancer drugs were approved based on trials where Black patients represented less than 5% of participants. Several drugs were approved with zero Black participants recorded.

<vegachart schema-url="{{ site.baseurl }}/extracredit1.json" style="width: 100%"></vegachart>

## Why This Matters

Clinical trials are not just a technical step in the drug approval process — they are the evidentiary foundation for every prescription a doctor writes. When a doctor tells a Black patient with lung cancer that a particular drug has a 40% response rate, that number was calculated almost entirely from trials in which people who look like that patient were barely present. We do not know if the true response rate for Black patients is higher or lower. We do not know if the side effect profile differs. We simply do not have the data.

The FDA has taken steps in recent years to encourage more diverse trial enrollment, and some drug sponsors have made public commitments to improve. But as this dataset shows, meaningful progress had not yet materialized by 2018. Closing this gap requires active effort from pharmaceutical companies, trial investigators, the FDA, and the communities themselves — including addressing well-documented barriers like geographic access to trial sites, historical mistrust of the medical system among Black Americans, and eligibility criteria that inadvertently exclude more diverse patients.

## Data Sources & Citations

- **Primary dataset:** ProPublica, *Clinical Trials: Participant Demographic Data* (2018). Compiled from FDA Drug Trials Snapshots, January 2015 – August 2018. [https://projects.propublica.org/datastore/#cancer-clinical-trials-demographics-data](https://projects.propublica.org/datastore/#cancer-clinical-trials-demographics-data). License: ProPublica Standard Terms of Use.

- **Cancer incidence by race:** National Cancer Institute, Surveillance, Epidemiology, and End Results (SEER) Program, Cancer Statistics Explorer, 2022. [https://seer.cancer.gov/statistics-network/explorer/](https://seer.cancer.gov/statistics-network/explorer/)

- **U.S. population by race:** U.S. Census Bureau, 2020 Decennial Census, Table P2. [https://data.census.gov/table/DECENNIALPL2020.P2](https://data.census.gov/table/DECENNIALPL2020.P2)

- **Original reporting:** Duehren, A., & Ornstein, C. (2018). *Black Patients Miss Out on Promising Cancer Drugs.* ProPublica. [https://www.propublica.org/article/black-patients-miss-out-on-promising-cancer-drugs](https://www.propublica.org/article/black-patients-miss-out-on-promising-cancer-drugs)

## Analysis Notebooks

- [Data Cleaning Notebook](https://github.com/aaliyahali/aaliyahali.github.io/blob/main/preprocess.ipynb)
- [Analysis & Visualization Notebook](https://github.com/aaliyahali/aaliyahali.github.io/blob/main/fp-part3.ipynb)
