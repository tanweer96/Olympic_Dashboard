# Olympic Dashboard

### Dashboard Link : https://github.com/tanweer96/Olympic_Dashboard/blob/main/Olympic%20Dashboard.pbix

## Overview

The Olympic Games have a rich history spanning over a century, with thousands of athletes competing for medals across various sports and disciplines. Analyzing such a vast dataset requires a structured approach to extract meaningful insights. This Power BI dashboard aims to provide an interactive and visually appealing way to explore Olympic data from 1896 to 2016.

## Problem Statements
#### Historical Olympic Data Analysis
How can we efficiently analyze Olympic medal trends across multiple years?
What are the patterns in medal distribution across different countries?

#### Country-Wise Performance
Which countries have been the most successful in terms of medal count?
How has each country’s performance evolved over different Olympic events?

#### Athlete Participation & Performance
How many athletes have participated in the Olympics over the years?
What is the gender distribution of athletes across different sports?
Which athletes have won the most medals in Olympic history?

#### Medal Distribution Insights
What is the distribution of gold, silver, and bronze medals over different years?
How do Summer and Winter Olympics compare in terms of total medals awarded?

#### Demographics & Trends
What are the trends in athlete age groups over different Olympic events?
How has gender representation changed over time in different sports?

#### Interactive Data Exploration
How can users filter data dynamically based on country, year, gender, and sports?
How can we present data in an easy-to-understand visual format using Power BI?

### Solution Approach
This Power BI dashboard addresses the above challenges by:  
✅ Providing interactive visualizations for medal analysis by year, country, and athlete.  
✅ Allowing users to filter data dynamically using dropdowns and slicers.  
✅ Visualizing gender-based and seasonal Olympic trends for better insights.  
✅ Displaying a world map to analyze athlete distribution by country.

## Steps

### A. Card Visual : 
### 1️⃣ Gold Medals Count 🏅 – 13K
📌 Purpose: Displays the total number of gold medals awarded.  
DAX:
    
    Total Gold Medals = 
    CALCULATE(
        COUNT(athlete_data[Medal]), 
        athlete_data[Medal] = "Gold"
    )

### 2️⃣ Silver Medals Count 🥈 – 13K
📌 Purpose: Displays the total number of silver medals awarded.  
DAX:
   
    Total Silver Medals = 
        CALCULATE(
            COUNT(athlete_data[Medal]), 
            athlete_data[Medal] = "Silver"
        )
### 3️⃣ Bronze Medals Count 🥉 – 13K
📌 Purpose: Displays the total number of bronze medals awarded.  
DAX:
    
    Total Bronze Medals = 
    CALCULATE(
        COUNT(athlete_data[Medal]), 
        athlete_data[Medal] = "Bronze"
    )
### 4️⃣ Total Medals Count 🏆 – 40K
📌 Purpose: Displays the total number of medals (Gold, Silver, and Bronze) awarded.  
DAX:
    
    Total Medals = COUNT(athlete_data[Medal])
### 5️⃣ Countries Participated 🌍 – 207
📌 Purpose: Displays the number of unique countries that have participated in the Olympics.  
DAX:
    
    Total Countries = DISTINCTCOUNT(athlete_data[Country])
### 6️⃣ Total Athletes Count 🏃‍♂️ – 135K
📌 Purpose: Displays the total number of athletes who participated in the Olympics.  
DAX:
    
    Total Athletes = DISTINCTCOUNT(athlete_data[Name])
### 7️⃣ Total Sports Played 🎯 – 765
📌 Purpose: Displays the number of unique sports played in Olympic history.  
DAX:

    Total Sports = DISTINCTCOUNT(athlete_data[Sport])
### 8️⃣ Total Teams Participated 🏅 – 1K
📌 Purpose: Displays the number of unique teams that have participated in the Olympics.  
DAX:

    Total Teams = DISTINCTCOUNT(athlete_data[Team])

### B. Bar Chart (Medals by Country)  

📌 Purpose:
Displays the total number of medals won by each country.
Gold (🟡), Silver (⚪), and Bronze (🟤) medals are shown in stacked bars.
The top countries (USA, Russia, Germany, UK, etc.) are leading in medal counts.
📌 DAX:

    Total Medals by Country = 
    CALCULATE(
        COUNT(athlete_data[Medal]),
        ALLEXCEPT(athlete_data, athlete_data[Country])
    )
📌 Insights: USA is the top medal-winning country.
Russia, Germany, and the UK follow closely behind.

### C. Donut Chart (Medals by Gender)
📌 Purpose: Shows the distribution of medals won by Male (M) and Female (F) athletes.
71.71% (29K medals) were won by males, and 28.29% (11K medals) were won by females.  
📌 DAX:

    Total Medals by Gender = 
    CALCULATE(
        COUNT(athlete_data[Medal]), 
        ALLEXCEPT(athlete_data, athlete_data[Sex])
    
📌 Insights: Male athletes have won more medals historically.
This highlights gender disparities in Olympic history.

### D. Donut Chart (Medals by Season)
📌 Purpose: Shows how many medals were won in Summer Olympics vs. Winter Olympics.
85.68% (34K medals) were won in Summer, while 14.32% (6K medals) were won in Winter.  
📌 DAX:

    Total Medals by Season = 
    CALCULATE(
        COUNT(athlete_data[Medal]), 
        ALLEXCEPT(athlete_data, athlete_data[Season])
    )
📌 Insights: Most Olympic medals come from Summer Games due to more events. Winter Olympics have fewer medals because they have fewer sports.

### E. Stacked Bar Chart (Medals by Year)
📌 Purpose: Shows how many medals (Gold, Silver, Bronze) were won each year from 1896 to 2016.
Helps analyze how the Olympics have evolved over time.  
📌 DAX:

    Total Medals by Year = 
    CALCULATE(
        COUNT(athlete_data[Medal]), 
        ALLEXCEPT(athlete_data, athlete_data[Year])
    )
📌 Insights: Olympic participation has grown over time, leading to more medals awarded.
The years 2008, 2016, and 2004 saw the highest medal counts.
Older Olympics (e.g., 1948, 1924) had fewer medals due to fewer participating countries and fewer events.

### F. Bar Chart (Athletes by Sport and Gender)
📌 Purpose: Shows the number of male (M) and female (F) athletes in different sports.
Athletics and Swimming have the highest participation.  
📌 DAX:

    Total Athletes by Sport & Gender = 
    CALCULATE(
        DISTINCTCOUNT(athlete_data[Name]), 
        ALLEXCEPT(athlete_data, athlete_data[Sport], athlete_data[Sex])
    )
📌 Insights: Athletics and Swimming have the highest number of athletes. Sports like Gymnastics and Sailing have lower participation.

### G. Bar Chart (Athletes by Country and Gender)
📌 Purpose: Displays the number of male (M) and female (F) athletes from each country. USA, Germany, UK, and France have the highest participation.  
📌 DAX:

    Total Athletes by Country & Gender = 
    CALCULATE(
        DISTINCTCOUNT(athlete_data[Name]), 
        ALLEXCEPT(athlete_data, athlete_data[Country], athlete_data[Sex])
    )
📌 Insights: USA has the highest number of athletes participating.
Germany, UK, and France have also sent large numbers of athletes.

### H. Bar Chart (Athletes by Age Band and Gender)
📌 Purpose: Displays athletes’ age distribution in different bands:
0-18
19-30
31-45
46-60
Most athletes are in the 19-30 age group.
📌 DAX:

    Total Athletes by Age Band & Gender = 
    CALCULATE(
        DISTINCTCOUNT(athlete_data[Name]), 
        ALLEXCEPT(athlete_data, athlete_data[Age Band], athlete_data[Sex])
    )
📌 Insights: Most Olympic athletes are aged 19-30.
Fewer athletes compete at older ages (46-60).

### I. Athletes by Medals (Bar Chart)
📌 Purpose: Displays top medal-winning athletes with their total Gold, Silver, and Bronze medals. Michael Phelps (Swimming) is the top medalist.  
📌 DAX:

    Total Medals by Athlete = 
    CALCULATE(
        COUNT(athlete_data[Medal]), 
        ALLEXCEPT(athlete_data, athlete_data[Name])
    )
📌 Insights: Michael Phelps has won the most medals. Athletes from swimming and athletics dominate the list.

### J. Map Visualization (Athletes by Country)
📌 Purpose: Shows the geographic distribution of athletes worldwide. Bigger pink dots indicate more athletes from that country.  
📌 DAX:

    Total Athletes by Country = 
    CALCULATE(
        DISTINCTCOUNT(athlete_data[Name]), 
        ALLEXCEPT(athlete_data, athlete_data[Country])
    )
📌 Insights: USA, Germany, France, Russia, and China have the highest number of Olympic athletes. Smaller countries have fewer athletes.

## Snapshot of Dashboard Page 1
![Page_1](https://github.com/tanweer96/Olympic_Dashboard/blob/main/Page_1.png)

## Snapshot of Dashboard Page 2
![Page_2](https://github.com/tanweer96/Olympic_Dashboard/blob/main/Page_2.png)
