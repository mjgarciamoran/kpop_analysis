# K-Pop Song Release and Analytics - Preliminary Data Quality Assessment

This repository contains the preliminary data quality assessment of the K-Pop song release and daily YouTube analytics data I have gathered and stored in the following repository: __[K-Pop Release Database with Daily Analytics](https://github.com/mjgarciamoran/kpop_release_database)__.

---
## Structure of the database
The database currently contains information spanning four years (2022–2025) across three types of analytics: comments, likes, and views.
This results in a total of __12 CSV files__, which I refer to as _analytics records_.

---

## Data quality assessment

Before diving into any sort of analysis, a general quality assessment of the dataset needs to be performed.
After verifying that data was successfully fetched each day, the next steps focus on identifying __duplicate entries__ and __missing (NaN) values__.

### Total videos, deduplication
To get an overview of the data, the total number of videos per year is shown, alongside the number of new videos added each day.

Since the song release data originates from a community-driven source, duplicate entries are relatively common.
By detecting and removing duplicates, we are left with __6,741 unique videos__.

<p align="center">
  <img src="./images/kpop_init_dedup.jpg" alt="Init 1">
  <!-- <img src="./images/example2.png" alt="Example 2" height="300"> -->
</p>
<p align="center">Visualizations of gathered videos and their deduplication.</p>

### Missing values

we conclude this quality assessment by detecting missing values.
To do this, we differentiate between 3 types of entries.

- `All-NaN entries` — Entries with missing values in all columns. These analytics have been unlisted (made private) before data collection for this project began.
- `Unlisted during fetching` — Entries that contain some valid values followed by missing ones, indicating that the video became unlisted during the data collection period.
- `Unexpected NaNs` — Entries with isolated missing values, typically only one per row. These are likely due to occasional fetching errors.

<p align="center">
  <img src="./images/kpop_init_nans.jpg" alt="Init 2">
  <!-- <img src="./images/example2.png" alt="Example 2" height="300"> -->
</p>
<p align="center">Visualization of NaN detection.</p>

It is worth noting that each video corresponds to 3 entries, one per analytic record. This means that the earlier count of 6,741 unique videos translates to __20,223 total entries__.

Additionally, wee can already infer some conclusions from this data; particularly from discrepancies in the number of all-NaN entries across different types of analytics.
For instance:
- The number of all-NaN entries in the views records determines the number of unlisted (unpublished or private) videos, since views cannot be made private in any other way.
- On the other hand, likes and comments can be manually hidden, allowing us to calculate how many videos have disabled likes and how many have disabled comments.

<p align="center">
  <img src="./images/kpop_init_unlistedvshidden.jpg" alt="Init 3" height="500">
</p>
<p align="center">Visualization of unlisted videos vs hidden analytics.</p>

<!--


---
## Secondary data quality assessment

discrepancies between kpopping dates and youtube dates

deleted analytics by youtube

-->
