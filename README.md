# Olympic-Statistics
Data visualization of Olympic Games with Power BI
- Data Source: Unknown provided by a instructor at BCIT
- Software: Microsoft Power BI

#### Calculate Team Ranking by Medal Weighting
```
Medal Score = SWITCH(TRUE(), Fact_Results[Medal] = "Gold", 3, Fact_Results[Medal] = "Silver", 2, Fact_Results[Medal] = "Bronze", 1, BLANK())
Total Medal Weighting = SUMX(Fact_Results,Fact_Results[Medal Score])
Ranking = RANKX(ALL(Countries[Country]),[Total Medal Weighting],,DESC)
Prev. Ranking = CALCULATE([Ranking],PARALLELPERIOD(Dates[Date], -4, YEAR))
```
