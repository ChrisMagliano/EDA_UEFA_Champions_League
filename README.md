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
Our comprehensive analysis of the UCL from the 1955-56 season to the 2022-23 season reveals several key insights into the competition's evolution and dynamics. 
### Team performances
Firstly we examined which teams dominate the competition based on their appearences and wins. 
![top10_matches](https://github.com/user-attachments/assets/0eb98b93-e4a6-4e21-81ba-bb6c48722c3d)
The previous plot clearly shows that **Real Madrid** is the most notable team in UCL competition with almost 500 games and nearly 300 wins.
The second team per played matches is **Bayern Munich** followed by **FC Barcelona**. Both teams played more than 300 matches in UCL but less than 400. It is impressive to notice that Real Madrid's wins almost corresponds to the total number of matches played by **Juventus** in its history, that is fourth in this classification.
Despite its clear dominance, this plot also suggests that Real Madrid is not the best team in terms of win/loss ratio (W/L), as shown in the plot below.

![top10_wlratio](https://github.com/user-attachments/assets/a1c8e833-0b01-4240-925c-368bc56efb37)
Indeed, Bayern Munich and FC Barcelona have slightly higher win/loss ratios compared to Real Madrid. Notably, the plot also highlights the emergence of teams such as **Manchester City** and **Paris Saint-Germain**, which are not among the top 10 teams in terms of UCL appearances. This suggests that while these teams lack a long-standing history in the UCL, they have become increasingly influential in the European football landscape in recent years ([Man City UCL](https://www.uefa.com/uefachampionsleague/history/clubs/52919--man-city/), [PSG UCL](https://www.uefa.com/uefachampionsleague/history/clubs/52747--paris-sg/)). We here stress that this conclusion was not possible based only on our datasets since it lacks information about the appearences of each team per years, but was the result of combination with the UEFA database. Moreover, for this analysis we selected only those teams with at least 50 matches in UCL. Thus, we avoided cases like that of [Zbrojovka Brno](https://www.fczbrno.cz/)	team that played UCL once in early 1960s with 1 win and 4 draws. Since it did not lose any match, it would have an unreliable W/L ratio.

We then analyzed the top five teams with the most UCL titles, along with the *best* runners-up in the competition’s history. Real Madrid clearly stands out with 14 titles, double the amount won by AC Milan and Bayern Munich, who are tied for second place. Conversely, Juventus has the highest number of UCL final losses, with 7 defeats, followed by Bayern Munich and SL Benfica, each with 5 losses.
![top_bot_finalist](https://github.com/user-attachments/assets/53ef8515-fae3-4f81-a9bb-0150c57a062e)


We also aimed to explore any potential relationship between the number of matches played and the number of wins. The left panel of the plot below illustrates the dataset with the number of matches as the independent variable and the number of wins as the dependent variable. A clear upward trend is evident, indicating that as the number of games increases, so do the number of wins. However, this trend is not merely a reflection of the [Law of Large Numbers](https://en.wikipedia.org/wiki/Law_of_large_numbers), which suggests that the number of wins should approximate the probability of winning times the number of matches. According to this principle, with a win probability of $1/3$, one would expect Real Madrid to win approximately $500/3 \approx 167$ games after $500$ matches. In reality, Real Madrid has won 291 out of $486$ matches, giving a win rate of about $59$ %. This discrepancy indicates that as a team plays more games, it gains valuable experience. The plot shows that up to around $100$ games, the number of wins is roughly one-third of the matches played. Beyond this point, it appears that teams have accumulated sufficient experience, leading to a winning probability of approximately $50$ % in UCL matches. When reaching the most dominant teams of the UCL competition (i.e. Real Madrid, Bayern Munich and FC Barcelona) the winning probability nearly corresponds to $60$ %.

To make this qualitative analysis statistical robust we performed two different regression on our dataset: *linear* fit and *quadratic* fit, then evaluate the $R^2$ [score](https://en.wikipedia.org/wiki/Coefficient_of_determination) score and the [**MSE**](https://en.wikipedia.org/wiki/Mean_squared_error). As evident from the right panel of the figure below, the quadratic fit outperformed the linear with a $MSE=19$ and $R^2=0.98$ against a $MSE=49$ and $R^2=0.95$ for the linear case.
Thus, this analysis would indicate that the process of learning and gaining expertise is not linear but more likely quadratic.
<p align="center">
<img src="https://github.com/user-attachments/assets/b9bd6ad7-69eb-4562-9a4c-1d59c070f3e3" alt="matches_wins" width="1000"/>
</p>
This result would make up a zero order step for a Machine Learning predictive algorithm as well as an interesting case of study for behavioral science. 

We conclude this subsection with the correlation matrix of some features of our dasets as shown below.
![all_time_corr](https://github.com/user-attachments/assets/3737b366-1b11-4caa-ab16-0c661ee5f2c3)
As expected the number of matches shows a slight positive correlation with the win ratio, as more wins typically result in more matches played. Similarly, the number of matches is negatively correlated with the loss ratio. Indeed, prior to 1991, the UEFA Champions League featured only a knockout format, so a single loss would eliminate a team from the competition. Since 1991, the competition has been revised to include a group stage, which ensures a minimum number of matches before teams advance to the knockout rounds (see [UEFA Champions League](https://en.wikipedia.org/wiki/UEFA_Champions_League) for reference).

### Finals analysis
#### Scores and goals
We keep our analysis by examining the available information about the UCL finals from 1955 to 2023. We started by observing that the most common score during a UCL final is **1-0** that occurred 19 times out of 69 finals ($\approx 27$ %). 
![top5_scores](https://github.com/user-attachments/assets/e150bb7b-b8c3-4541-b761-6610a30d2843)
A 1-0 scoreline indicates a tightly contested match, reflecting the high stakes and defensive strategies typical of UCL finals. Teams in these high-pressure games often prioritize solid defense and tactical discipline, leading to fewer goals. This scoreline suggests that the finalists are well-matched, with defenses usually able to contain the attacking play, and a single goal often proving sufficient to secure victory.

Historically, UCL finals have often been decided by narrow margins, in fact **2-1** and **2-0** are respectively the second and third most frequent score ($10$ and $8$ times respectively). 
This trend may reflect the competitive nature of the tournament, where the difference in quality between teams is minimal, leading to close encounters. However, it's also worth considering that tactics and game strategies evolve, and what has been observed in past finals might change as teams adapt their approaches to match the modern game. 
In this regard, the plot below shows the mean total goals scored during a UCL final per decade. 
![goals_per_decade](https://github.com/user-attachments/assets/c288a0d5-e4a5-4154-aeeb-7e2fe0a6545a)

The 1960s were particularly prolific, highlighted by the thrilling [7-3](https://www.uefa.com/uefachampionsleague/match/61542--real-madrid-vs-eintracht-frankfurt/) showdown between Real Madrid and Eintracht Frankfurt, a standout victory for *Los Blancos*. Over the decades, however, there has been a noticeable fluctuation in goal-scoring, with the 1980s and 2020s emerging as the least prolific periods, averaging just $1.40$ and $1.00$ total goals per match, respectively. We argue that 2020s only consist of three matches (Chelsea FC - Manchester City	1–0, Real Madrid - FC Liverpool 1-0 and Manchester City - Inter Milan 1-0) with respect to the $10$ matches of the 1980s.
The fluctuations in UCL final's goal-scoring over the years might be attributed to different factors and their complex combination:
- **Tactical Evolution**: football tactics have evolved significantly over the decades. In earlier years, teams often favored more attacking styles, leading to higher-scoring games. As the game evolved, many teams adopted more defensive, strategic approaches, especially in high-stakes finals, resulting in fewer goals;
- **Physical and Technical Development**: Over time, players have become more physically fit and technically proficient, allowing teams to execute more complex defensive strategies. The increased fitness levels also mean players can maintain a high level of defensive intensity throughout the match;
- **Offensive Innovations**: During the 2000s and 2010s, football saw the emergence of more dynamic and versatile attacking strategies. Teams like Barcelona under Pep Guardiola, and later Real Madrid, focused on high-tempo, possession-based, and counter-attacking football, which often led to more open and higher-scoring games;
- **Star Players and Super Teams**: These decades were characterized by the rise of “super teams” with an abundance of world-class attacking talent. The presence of players like Lionel Messi, Cristiano Ronaldo, and other top forwards meant that finals were often decided by moments of individual brilliance, leading to more goals;
- **Advances in Sports Science**: Improvements in sports science, fitness, and recovery might have allowed players to maintain higher intensity levels throughout the game, contributing to more dynamic and open matches with greater goal-scoring potential.

We stress that these are only a few possible factors influencing the total goal scored in a UCL final across the years. However, there exist many other random or psychological factors which highly influence the final result.

Our analysis also reveals that the majority of matches, 51 out of 69, have been decided during regular time, showcasing the dominance of teams in securing a result within the standard 90 minutes. However, for more evenly matched finals, the outcome has extended beyond regular time: 11 finals were decided by penalty shoot-outs, 5 in extra time, and 2 required a [replay](https://en.wikipedia.org/wiki/1974_European_Cup_final). These statistics highlight the intense and competitive nature of the tournament, where a significant number of finals required additional time to determine a winner.
<p align="center">
<img src="https://github.com/user-attachments/assets/a0ada829-fe37-48f3-baf1-629939431f2d" alt="matches_wins" width="500"/>
</p>

Next, we sought to determine whether playing a UEFA Champions League final in one's home country offers any psychological advantage.
<p align="center">
<img src="https://github.com/user-attachments/assets/6945f880-2911-4e37-b6c4-8a782c9c68c6" alt="pie_home" width="500"/>
</p>
As shown in the pie chart above, teams playing on home soil have won the UCL final 58.3% of the time, compared to a 41.7% loss rate. This was expected since the familiarity with the stadium, local climate, and pitch conditions likely give the home team a physical advantage. Additionally, the psychological boost from having the majority of the crowd's support can enhance player performance and confidence. These elements, combined with reduced travel fatigue, might contribute to the observed increase in success for home-country teams.

The home-field advantage is also evident in the number of goals scored by the home team compared to those by the visiting team. The plot below clearly shows that the distribution of goals for the home team is skewed towards higher values. Indeed, the mean value of total goals scored by the home team is $1.67$ compared to $1$ for visiting club.
![goals_home_visitor](https://github.com/user-attachments/assets/e46bda8f-af5e-46fb-8c27-55b11eee7633)
We wanted to statistically test the difference between the two distributions using the [Mann-Whitney U test](https://en.wikipedia.org/wiki/Mann%E2%80%93Whitney_U_test). We opted for this non-parametric algorithm because data are not normally distributed ([Shapiro-Wilk](https://en.wikipedia.org/wiki/Shapiro%E2%80%93Wilk_test) test returned $p<0.05$ in both cases) and both sample contain only 12 elements. However, the test yields a $p=0.09$ thus we cannot reject the null hypothesis with 95% confidence level.

#### Attendance
We conclude our analysis by examining the attendance at the UCL final over the years as shown in the plot below.
![attendance_years](https://github.com/user-attachments/assets/a58b7508-c719-4623-add2-1e9da7011fa5)
The data reveals variations in attendance across different decades, with the highest recorded attendances being 124,000 in 1957 at the **Santiago Bernabéu Stadium** in Madrid and 127,621 in 1960 at **Hampden Park** in Glasgow. Both matches were victories for Real Madrid. While the substantial turnout in 1957 was expected due to the final being held at the Santiago Bernabéu, the even larger crowd in 1960 in Scotland underscores the extensive fanbase of Real Madrid. 
We also highlight the significant drop in attendance during the 2020 final, which saw an attendance of zero due to the COVID-19 pandemic. This unprecedented situation led to the postponement and eventual rescheduling of the match, with the final being played in a restricted environment without fans in attendance. The pandemic's impact on global sporting events is starkly reflected in this anomaly, underscoring how external factors can drastically affect match-day experiences and attendance figures. The effects of the pandemic were also evident in attendance in 2021, with only 33% of the do Dragao stadium's capacity open to supporters.

As already mentioned in the case of 1957 final, the attendance fluctuations are mostly determined by the participation of a team playing the final in its own country. The boxplot below shows the attendance if one of the two teams are playing in their home country or not. 
<p align="center">
<img src="https://github.com/user-attachments/assets/e22e9e72-4911-4d18-8ddb-5770ad8aa606" alt="matches_wins" width="600"/>
</p>
There is a clear difference between the two distributions, with the former (goals scored by team playing in their home country) shifted towards larger values on average with respect to the latter. We statistically confirmed this difference by employing the *Mann-Whitney U test* that allows us to reject the null hypothesis (i.e. the two samples come from the same distribution) with a $p < 0.05$. 

Lastly, we examined which country has the highest average attendance. The left panel of the plot below highlights the top five countries by average attendance, regardless of how often they have hosted events. Interestingly, Yugoslavia leads the rankings, with an average of nearly 90,000 attendees, primarily due to the 1972-73 season when AFC Ajax defeated Juventus 1-0 in Belgrade. Because Yugoslavia did not host many finals, this one high-attendance event significantly boosts the country's average.
Scotland follows with just under 80,000 attendees, but this finding is heavily influenced by the 1960 final (Real Madrid vs. Eintracht Frankfurt, 7-3), while the other two events barely reached $50,000$ attendees.

![top_venues](https://github.com/user-attachments/assets/e096ea4d-6736-44ee-b71b-4ea88630c6db)
Recognizing the limitations of this approach, we also narrowed the analysis to countries that have hosted at least four times (right panel). When the analysis is limited to countries that have hosted at least four times, the results change. Countries like England and Spain, which have hosted multiple finals over the years, show more consistent and high average attendance. This consistency suggests these countries have larger or more frequently used venues, better infrastructure, and possibly a stronger football culture, leading to consistently high turnout. Italy also ranks highly under this refined criterion, indicating a strong and consistent interest in football events.

We conclude our analysis by showing the correlation heatmap between the features of the `finals` dataset seeking for correlations.
![finals_corr](https://github.com/user-attachments/assets/a107bafc-20fa-438c-a9f4-a8922dc14048)
We found no significant relationship, but there is a mildly positive correlation between attendance and instances where one of the finalists is playing in their home country as already discussed before.


## Recommendations and Insights


## Limitations

## References
1. [Manchester City UCL History](https://www.uefa.com/uefachampionsleague/history/clubs/52919--man-city/)
2. [Paris Saint-Germain UCL History](https://www.uefa.com/uefachampionsleague/history/clubs/52747--paris-sg/)
3. [UEFA Champions League](https://en.wikipedia.org/wiki/UEFA_Champions_League) 
