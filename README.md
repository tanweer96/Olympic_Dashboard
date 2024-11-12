# Olympic Dashboard

### Dashboard Link : https://github.com/tanweer96/Olympic_Dashboard/blob/main/Olympic%20Dashboard.pbix

## Summary

This dashboard provides a comprehensive analysis of Olympic data, offering insights into historical trends, athlete demographics, and medal distributions across different countries, athletes and sports. The dashboard is divided into two pages:

### Medals Page:

## Steps

-1. Card Visual : Four card visuals for different types of medals such as for Bronze, Silver, Gold and Total Medals
For creating above four card visuals, four New measure was created,

Bronze = SUM(Table_1[Bronze_Medals])

Silver = SUM(Table_1[Silver_Medals])

Gold = SUM(Table_1[Gold_Medals])

Total Medals = [Gold] + [Silver] + [Bronze]

-2. Clustered Bar Chart : To show distribution of medals (Bronze, Silver and Gold) by country.

-3. Donut Chart : To analyze Distribution of medals by Gender.

-4. Donut Chart : To analyze Distribution of medals by Season.

-5. Clustered Bar Chart : To show distribution of medals (Bronze, Silver and Gold) by Year.


Athletes Page:

-1. Card Visual : Four card visuals for countries participated, total athletes, sports played and total team which have participated in the olympics
For creating above four card visuals, four New measure was created,

Country Participated = DISTINCTCOUNT(Table_2[region])
Total Athletes = DISTINCTCOUNT(Table_1[Name])
Sports Played = DISTINCTCOUNT(Table_1[Event])
Total Team = DISTINCTCOUNT(Table_1[Team])

-2. Clustered Bar Chart : To visualize how many males and females athletes are there respective to the sports.

-3. Map Visual : To analyze athletes from different countries.

-4. Clustered Bar Chart : To show males and females athletes respective to the country.

-5. Clustered Bar Chart : To get visual the how many medals (Bronze, Silver and Gold) was earned by an individual athlete in descending order.

-6.  Clustered Column Chart : To analyze how many athletes are in age band of 0-18, 19-30, 31-45, and 46-60.

## Snapshot of Dashboard Page 1
![Page_1](https://github.com/tanweer96/Olympic_Dashboard/blob/main/Page_1.png)

## Snapshot of Dashboard Page 1
![Page_2]()
