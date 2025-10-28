# K-Pop Analysis

This repository contains my analysis of song release and analytics data from the database I have previously fetched in this project: [K-Pop Release Database with Daily Analytics](https://github.com/mjgarciamoran/kpop_release_database).

---

## Preliminary data quality assessment

First we do a health check of the data. After verifying that data has been fetched everyday I check for duplicates and nans.

<p align="center">
  <img src="./pics/kpop_init_dedup.jpg" alt="Example 1">
  <!-- <img src="./images/example2.png" alt="Example 2" height="300"> -->
</p>
<p align="center">Example of the first and last pages of the leaderboard of a particular gamemode and region.</p>

Bear in mind that each video corresponds to 3 entries, one in each analytic record, so 6741*3 = 20223

<p align="center">
  <img src="./pics/kpop_init_nans.jpg" alt="Example 1">
  <!-- <img src="./images/example2.png" alt="Example 2" height="300"> -->
</p>
<p align="center">Example of the first and last pages of the leaderboard of a particular gamemode and region.</p>
