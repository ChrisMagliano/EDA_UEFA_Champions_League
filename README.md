# UEFA Champions League 1955-2023

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning & Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Results and findings](#results-and-findings)
- [Recommendations and Insights](#recommendations-and-insights)
- [Limitations](#limitations)
- [References](#references)
 

### Project Overview
In this project I have performed a complete Data Exploration of the UEFA Champions League (UCL) history from the 1955-56 season up to the 2022-23 season. Through the analysis of multiple details on matches and team performances, my goal is to uncover patterns, establish benchmarks, and achieve a more profound understanding of the UCL competition.

### Data Sources
The datasets used in this project `UCL_AllTime_Performance_Table.csv` and `UCL_Finals_1955-2023.csv` were retrieved on [Kaggle](https://www.kaggle.com/datasets/fardifaalam170041060/champions-league-dataset-1955-2023). Both offer detailed insights into match results and team performances spanning decades of Europe's top club football competition. In particular `UCL_AllTime_Performance_Table.csv` contains information about the UCL teams performances (e.g. number of matches, wins, draws and losses), while `UCL_Finals_1955-2023.csv` includes several metrics about each UCL final as the winners, runners-up, attendance etc.
We acknwoledge [Fardifa Fathmiul Alam](https://www.kaggle.com/datasets/fardifaalam170041060/champions-league-dataset-1955-2023) for the detailed data files description listed below.

**Finals Details (1955-56 to 2022-23)**
- `Season`: The football season during which the final was played.
- `Country`: The home country of the winning team.
- `Winners`: The name of the winning team.
- `Score`: The final score at the end of the match.
- `Runners-up`: The team that finished second.
- `Country`: The home country of the runners-up.
- `Venue`: Location of the final match.
- `Attendance`: Number of spectators present at the venue.
- `Notes`: Additional information such as whether the match went into extra time or any other notable events.

**Team Performances (Aggregate Data)**
- `Team`: Name of the team.
- `M.` (Matches Played): Total number of matches played by the team in the Champions League.
- `W` (Wins): Total wins.
- `D` (Draws): Total draws.
- `L` (Losses): Total losses.
- `Goals`: Goals scored against goals conceded.
- `Dif` (Goal Difference): Goal difference.
- `Pt` (Points): Points accumulated based on match outcomes.

### Tools
The whole data preprocessing and visualization has been performed by means of [Python](https://www.python.org/downloads/) programming language and [Jupyter Notebook](https://jupyter.org/install) platform. It is accessible throughout the `UEFA_Champions_League.ipynb` file.

### Data Cleaning and Preparation
The first step of this project regards the data loading and preprocessing. I performed the following taks:
1. **Data loading and inspection**;
2. **Handling missing values**;
3. **Data cleaning** (drop useless columns and duplicated) and **formatting**.

All the details about this step are contained in the `UEFA_Champions_League.ipynb` jupyter notebook.

### Exploratory Data Analysis
Exploratory Data Analysis (EDA) process consists of exploring the dataset to answer key questions, such as:
- Which teams have been the most successful in terms of wins, finals appearances, and consistent performance?
- Which countries have produced the most successful teams?
- How do teams' performances differ when playing at home versus away?
- What are the trends in match attendance over the years, and how do they vary by country or venue?


## Results and findings

## Recommendations and Insights


## Limitations

## References
None.
