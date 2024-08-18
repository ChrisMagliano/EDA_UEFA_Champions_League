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
Our comprehensive analysis of the UCL from the 1955-56 season to the 2022-23 season reveals several key insights into the competition's evolution and dynamics. Firstly we examined which teams dominate the competition based on their appearences and wins. 
![top10_matches](https://github.com/user-attachments/assets/0eb98b93-e4a6-4e21-81ba-bb6c48722c3d)
The previous plot clearly shows that **Real Madrid** is the most notable team in UCL competition with almost 500 games and nearly 300 wins.
The second team per played matches is **Bayern Munich** followed by **FC Barcelona**. Both teams played more than 300 matches in UCL but less than 400. It is impressive to notice that Real Madrid's wins almost correspondly to the total number of matches played by **Juventus** in its history, that is fourth in this classification.
Despite its clear dominance, this plot also suggests that Real Madrid is not the best team in terms of win/loss ratio (W/L), as shown in the plot below.

![top10_wlratio](https://github.com/user-attachments/assets/a1c8e833-0b01-4240-925c-368bc56efb37)
Indeed, Bayern Munich and FC Barcelona have slightly higher win/loss ratios compared to Real Madrid. Notably, the plot also highlights the emergence of teams such as **Manchester City** and **Paris Saint-Germain**, which are not among the top 10 teams in terms of UCL appearances. This suggests that while these teams lack a long-standing history in the UCL, they have become increasingly influential in the European football landscape in recent years ([Man City UCL](https://www.uefa.com/uefachampionsleague/history/clubs/52919--man-city/), [PSG UCL](https://www.uefa.com/uefachampionsleague/history/clubs/52747--paris-sg/)).   

<p align="center">
<img src="https://github.com/user-attachments/assets/b9bd6ad7-69eb-4562-9a4c-1d59c070f3e3" alt="matches_wins" width="1000"/>
</p>

![all_time_corr](https://github.com/user-attachments/assets/3737b366-1b11-4caa-ab16-0c661ee5f2c3)

![top_bot_finalist](https://github.com/user-attachments/assets/53ef8515-fae3-4f81-a9bb-0150c57a062e)

![top5_scores](https://github.com/user-attachments/assets/e150bb7b-b8c3-4541-b761-6610a30d2843)

![goals_per_decade](https://github.com/user-attachments/assets/c288a0d5-e4a5-4154-aeeb-7e2fe0a6545a)

<p align="center">
<img src="https://github.com/user-attachments/assets/a0ada829-fe37-48f3-baf1-629939431f2d" alt="matches_wins" width="500"/>
</p>

![attendance_years](https://github.com/user-attachments/assets/a58b7508-c719-4623-add2-1e9da7011fa5)

![top_countries](https://github.com/user-attachments/assets/5865ba04-adc7-4e9f-8902-e2bc4bf06abf)


<p align="center">
<img src="https://github.com/user-attachments/assets/e22e9e72-4911-4d18-8ddb-5770ad8aa606" alt="matches_wins" width="600"/>
</p>


<p align="center">
<img src="https://github.com/user-attachments/assets/6945f880-2911-4e37-b6c4-8a782c9c68c6" alt="top10_matches" width="500"/>
</p>

![finals_corr](https://github.com/user-attachments/assets/cb22587b-0e31-44aa-8fcb-3e3627905d99)

![goals_home_visitor](https://github.com/user-attachments/assets/e46bda8f-af5e-46fb-8c27-55b11eee7633)

## Recommendations and Insights


## Limitations

## References
[Manchester City UCL History](https://www.uefa.com/uefachampionsleague/history/clubs/52919--man-city/)
[Paris Saint-Germain UCL History](https://www.uefa.com/uefachampionsleague/history/clubs/52747--paris-sg/)
