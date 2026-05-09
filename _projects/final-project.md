---
name: Who Gets Left Out? Race and Representation in Clinical Drug Trials
tools: [Python, Altair, Jekyll]
image: assets/pngs/cancer_trials.png
description: An interactive data journalism article examining racial and demographic disparities in FDA clinical drug trial participation from 2015 to 2018.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

# Who Gets Left Out? Race and Representation in Clinical Drug Trials

**Authors: Aaliyah Ali, Roqaya Elmenshawy, Livia Lin, Noor Esily**

---

## The Promise of a New Drug — And Who It's Tested On

When the U.S. Food and Drug Administration (FDA) approves a new drug, it is making a guarantee to the public: this medicine is safe and effective. But safe and effective *for whom*? Every drug approval is based on data collected from clinical trials — carefully controlled studies where real patients take an experimental drug and researchers measure the results. If the patients enrolled in those trials do not look like the people who will eventually take the drug, the results may not apply equally to everyone.

Between January 2015 and mid-August 2018, the FDA approved 155 new drugs and compiled demographic snapshots for each — recording what percentage of trial participants were White, Black, Asian, women, or over the age of 65. ProPublica, an investigative news organization, compiled all of these snapshots into a single dataset and used it to investigate racial representation in cancer drug trials. Our analysis expands that investigation across all disease categories — from cancer to infectious disease to cardiovascular conditions — revealing a systematic pattern of underrepresentation that is worst precisely where the stakes are highest.

---

## The Interactive Dashboard

The dashboard below lets you explore the full picture yourself. Use the **dropdown menu** to switch between demographic groups — Black participants, White participants, Asian participants, Women, and patients aged 65 and older. The **top bar chart** shows the average participation rate for the selected demographic broken down by disease category. **Click any bar** to filter the histogram below and see how individual drugs within that category are distributed. **Double-click** to reset back to all categories.

<vegachart schema-url="{{ site.baseurl }}/assets/json/interactive-dashboard.json" style="width: 100%"></vegachart>

A few patterns worth exploring:

- Select **Black / African American** and click **Infectious Disease** — participation jumps to ~21%, the highest of any category, largely driven by HIV and Hepatitis C trials that actively recruit from communities with higher disease prevalence.
- Stay on **Black / African American** and click **Cancer** — participation drops to ~3%, and the histogram shows most drugs clustered near zero. This is the most alarming finding in the entire dataset.
- Switch to **Cardiovascular** — Black participation falls to ~3.6% despite the fact that Black Americans face disproportionately high rates of heart disease and hypertension.
- Switch to **Women** — participation is above 50% in Cancer trials largely because breast, ovarian, and cervical cancer trials enroll only women. Neurological and Cardiovascular trials fall below the parity line.

---

## Cancer: Where the Gap Is Most Dangerous

Of all the disparities in this dataset, the one in cancer drug trials is the most troubling. The chart below compares cancer incidence rates by race over the same 2015–2018 window using data from the National Cancer Institute's SEER program. Black Americans have the highest cancer incidence rate of any group — yet they are nearly absent from the trials used to prove that cancer drugs work.

<vegachart schema-url="{{ site.baseurl }}/assets/json/contextviz1.json" style="width: 100%"></vegachart>

*Source: National Cancer Institute, SEER Cancer Statistics Explorer. [seer.cancer.gov](https://seer.cancer.gov/statistics-network/explorer/)*

This chart shows cancer incidence rates per 100,000 people by race from 2015 to 2018. Black Americans consistently have the highest rates — higher than White, Asian, or Hispanic Americans — yet as we saw in the dashboard, they make up only about 3% of cancer drug trial participants. The disconnect between who bears the greatest disease burden and who is represented in the research meant to address it is stark and consequential.

When normalized to compare directly against trial participation, the gap becomes even clearer. The chart below compares each group's share of U.S. cancer cases against their share of cancer drug trial participants. Black Americans account for roughly 37% of cancer cases among these three racial groups but only about 3% of cancer trial participants — an over ten-fold disproportion.

<vegachart schema-url="{{ site.baseurl }}/assets/json/contextviz2.json" style="width: 100%"></vegachart>

*Source: NCI SEER 2015–2018 (cancer incidence); ProPublica/FDA Drug Trials Snapshots (trial participation).*

---

## A Drug-by-Drug Look

The dot plot below shows every individual FDA-approved cancer drug from this period, sorted by the percentage of Black participants in its trial. Each dot is one drug. The clustering near zero is unmistakable — the vast majority of cancer drugs were approved on the basis of trials where Black patients represented less than 5% of participants. Several drugs were approved with effectively zero Black participants recorded.

<vegachart schema-url="{{ site.baseurl }}/assets/json/extracredit1.json" style="width: 100%"></vegachart>

---

## Why This Matters

Clinical trials are not just a technical step in the drug approval process — they are the evidentiary foundation for every prescription a doctor writes. When a physician tells a Black patient with lung cancer that a particular drug has a 40% response rate, that number was calculated almost entirely from trials where people who look like that patient were barely present. We do not know if the true response rate for Black patients is higher or lower. We do not know if the side effect profile differs. We simply do not have the data, because those patients were not in the room when the data was collected.

Cancer biology is not race-neutral. Certain cancers — like triple-negative breast cancer — disproportionately affect Black women and respond differently to treatment than the forms of breast cancer more common in White women. If clinical trials for breast cancer drugs enroll 75% White participants and 3% Black participants, the approved drug may be optimized for a biology that does not represent the patients who need it most. This is not a hypothetical concern — researchers have documented differences in drug metabolism, tumor biology, and treatment response across racial groups that make diverse trial enrollment a scientific necessity, not just an equity aspiration.

The FDA has taken steps in recent years to encourage more diverse trial enrollment, including issuing guidance documents on diversity action plans for clinical trials. But as this dataset shows, meaningful progress had not yet materialized during the 2015–2018 period. Closing this gap requires active effort from pharmaceutical companies, trial investigators, the FDA, and the communities themselves — including addressing well-documented barriers like geographic access to trial sites, historical mistrust of the medical establishment among Black Americans, and eligibility criteria that inadvertently screen out more diverse patient populations. The data makes clear that this is not a problem solving itself on its own.

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
  <a href="https://github.com/aaliyahali/aaliyahali.github.io/blob/main/python_notebooks/01_data_cleaning.ipynb" class="btn btn-outline-dark">
    Data Cleaning Notebook
  </a>
  <a href="https://github.com/aaliyahali/aaliyahali.github.io/blob/main/python_notebooks/fp-part3.ipynb" class="btn btn-outline-dark">
    Analysis & Visualization Notebook
  </a>
  <a href="https://raw.githubusercontent.com/aaliyahali/aaliyahali.github.io/main/assets/json/clinical_trials_cleaned.csv" class="btn btn-outline-dark">
    Cleaned Dataset (CSV)
  </a>
</div>