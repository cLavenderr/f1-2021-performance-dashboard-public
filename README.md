# 2021 Formula 1 Performance Analytics Dashboard

<p align="center">
  <img src="https://cdn.phototourl.com/free/2026-07-24-0a8a08b7-464e-4b18-981b-51b64ed7e5e4.png" alt="Formula 1 Logo" width="300">
</p>

<p align="center">
  <img src="https://cdn.imageurlgenerator.com/uploads/d1b6f187-c3bc-4e94-ab6c-aba71ea20f35.gif" alt="Dashboard Walkthrough Demo" width="900">
</p>

## 1. Executive Summary

Formula 1 generates large volumes of data, but raw datasets can be difficult to interpret and compare across an entire season. This project analyses driver and team performance across all 22 races of the 2021 season, transforming race data into a Power BI dashboard.

Using Excel for initial exploratory analysis and Power BI for data preparation and visualisation, the dashboard combines interactive visualisations with DAX driven measures, allowing analysis of driver consistency, team performance, and circuit specific trends. Potential future improvements include:
- Additional seasons (earlier and later)
- Tyre strategy data to evaluate their effectiveness
- Automating data refresh as new race data becomes available

## 2. Business Problem

Formula 1 performance data is often stored across multiple datasets, making it difficult for analysts and stakeholders to efficiently compare driver and team performance throughout a season. The lack of a centralised view limits the ability to identify performance trends, evaluate competitiveness, and generate actionable insights to support development.

## 3. Methodology

**Phase 1: Excel Prep & Prototyping**
- Cleaned and structured raw race data across multiple relational tables (largest table 500 rows), cleaning inconsistent timing and lap count formats alongside correcting driver names to build a reliable baseline dataset
- Calculated basic stats such as podium counts and championship position using XLOOKUP, RANK.EQ, and MAX
- Prototyped the dashboard layout with Pivot Tables and charts to map out performance trends before building in Power BI. This gave me an idea which visuals were worth building before investing time in the full dashboard. More advanced metrics (win %, podium rate, gap intervals) were built later in DAX

<p align="center">
  <img src="https://cdn.phototourl.com/free/2026-07-24-b25c60eb-8342-4419-b105-e875459af575.png"">
</p>

**Phase 2: Power BI Dashboard & Visuals**
- Merged and transformed relational tables in Power Query, optimising text columns and data types to support STAR schema modelling
- Wrote DAX measures to calculate win percentage, podium rate, and gap intervals
- Designed a dynamic portrait card that displays a driver's photo on slicer selection, defaults to the F1 logo when cleared
- Built a track visual that updates the circuit map and stats based on slicer selection
- Consolidated all metrics into a single dashboard view spanning the full 22 race season

![Logo](https://cdn.phototourl.com/free/2026-07-24-dec9fe36-32d0-4a9c-baf7-0733dcd0e20b.png)

## 4. Skills Demonstrated

Excel: Formulas (such as XLOOKUP, RANK,EQ, MAX, FILTER), Pivot Tables and Visualisations

Power BI: DAX, Power Query, ETL, Data Modelling (STAR schema) and Data Visualisation,


## 5. Results & Business Recommendation

**Results:**
- Joined 22 races of driver and team data across relational tables from multiple sources into one interactive dashboard, replacing the need to manually cross reference with simple slicer selection.
- Podium counts across the grid: Verstappen led with 18 podiums, followed by Hamilton (17), Bottas (11), and Perez (5). This showed Mercedes and Red Bull's constructor domination with no other team even being present in the top 4 podium counts.
- The dashboard highlights that the title was ultimately decided by a margin of just 8 points (395.5 vs 387.5) between the top two drivers over the race season. One of the closest and most controversial championship battles in F1 history.
  
<p align="center">
  <img src="https://i.postimg.cc/NFrGqqpp/yuh-(1).png"/>
</p>

- Redbull secured a podium in 19 of 22 races, Mercedes in 21 of 22, both teams showed near total podium consistency across the season with Mercedes only missing out on the podium once when Redbull made it and Redbull missing it 5 times when Mercedes made it. Mercedes was ultimately more reliable but Redbull still managed to sweep out the drivers championship from Mercedes.

**Recommendation:**
Given how tight the podium and points gap was between the top contenders, my dashboard is well suited to media/fan engagement use cases where the aim of the story is the closeness of the competition. Being able to instantly pull up metrics for drivers makes that story immediately visible to the viewers rather than being buried in a spreadsheet. Because the driver card and track visual are slicer driven, the same structure could potentially be used with any season's data assuming the data format is the same and track maps are available.

## 6. Next Steps

- Implement tyre strategy data to add a further metric to compare between drivers. 
- Automate data refresh so the dashboard updates as new race data becomes available.
- Further develop the model to support multi season (older and newer) comparison for tracking driver/team trends over time

