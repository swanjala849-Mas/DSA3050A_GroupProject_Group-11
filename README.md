# DSA3050A_GroupProject_Group-11
Olympic Sports Performance Dashboard
## Members
Student Name: Masika Sylvesta Wanjala 671815
## Project Overview
The Olympic Sports Performance Dashboard is a Business Intelligence project developed using Microsoft Power BI and Excel to analyze historical Olympic Games data from 1896 to 2016. The project transforms raw Olympic data into interactive visualizations that provide insights into athlete participation, medal achievements, country performance, and sport dominance.
## Dataset Source URL:
https://www.kaggle.com/datasets/mysarahmadbhat/120-years-of-olympic-history?select=athlete_events.csv
## Dataset Description
Dataset Name: 120 Years of Olympic History.
The dataset has 217117 rows and 18 columns.
The dataset contains historical Olympic Games data from 1896 to 2016 covering both Summer and Winter Olympics. It includes athlete demographics, event participation, country representation, and medal achievements.
## Business Problem
National Olympic Committees and sports governing bodies require a better understanding of the factors that contribute to Olympic success. However, the large volume of historical Olympic data makes it difficult to identify trends in athlete participation, medal performance, country rankings, and sport specialization. This project develops an interactive Power BI dashboard that analyzes Olympic data to uncover patterns in athlete characteristics, participation trends, country performance, and medal distribution. The insights generated can support strategic decisions related to athlete development, resource allocation, and sports performance management.

## Power Query Transformations
The following data preparation steps were carried out in Power Query:
- Rename columns 
- Correct data types 
- Remove duplicates 
- Remove blank rows 
- Trim and clean 
- Replace inconsistent values 
- Handle missing values 
- Remove unnecessary columns 
- Create custom and conditional columns 
### Advanced Transformations 
- Column profiling 
- Handle errors 
- Referenced queries  
- Nested conditions 
- Date table 
- Group by with multiple aggregations 

## Data Model Explanation
A Star Schema data model was implemented to improve performance and support efficient reporting.
Fact Table
Factathlete_events
Contains Olympic participation and medal records.

Dimension Tables
DimAthlete
Contains athlete information such as:
- Name
- Gender
- Age
- Height
- Weight
- BMI

DimDate
Contains:
- Year
- Decade
- Olympic Era

DimSport
Contains:
- Sport
- Sport rank

DimCountry
Contains:
- Country
- Team


### Data Model shown below
<img width="1366" height="674" alt="Modelling" src="https://github.com/user-attachments/assets/f3794703-1f29-4ce2-82a5-00996db72e76" />


## DAX Measures Created
- Total Athletes = DISTINCTCOUNT(athlete_events[Name])
- Total Medals =
CALCULATE(
COUNTROWS(athlete_events),
  (athlete_events[Medal) <> "No Medal"
)   
- Total Medal Score =
SUM(athlete_events[Medal Score])
- Average Athlete Age =
AVERAGE(DimAthlete[Age])
- Average BMI =
AVERAGE(DimAthlete[BMI])
- Average Height =
AVERAGE(DimAthlete[Height])
- Average Weight =
AVERAGE(DimAthlete[Weight])
- Country Rank =
RANKX(
ALL(DimCountry[Team]),
[Total Medals]
) 
- Sport Rank =
RANKX(
ALL(DimSport[Sport]),
[Total Medals]
)

## Dashboard Pages Explained
### 1. Executive Summary
Provides an overview of Olympic performance through:
- Total Athletes
- Total Medals
- Medal Distribution
- Top Countries
- Top Sports

<img width="876" height="503" alt="Executive Page" src="https://github.com/user-attachments/assets/a819f664-37fa-4f33-a4aa-4be37359ec93" />

### 2. Trend Analysis
Examines historical Olympic trends including:
- Athlete Participation Trend
- Medal Performance Trend
- Olympic Growth Analysis
<img width="887" height="503" alt="Trend Analysis" src="https://github.com/user-attachments/assets/7d306278-d492-4de3-9e4f-6cd16b964c11" />

### 3. Athlete Profile Analysis
Analyzes athlete characteristics:
- Age Distribution
- BMI Analysis
- Gender Distribution
- Height and Weight Relationships
- Performance Categories

<img width="890" height="512" alt="Athlete Profile Analysis" src="https://github.com/user-attachments/assets/cc2b690c-2ec3-4c4f-8bc6-887c16046ad2" />

### 4. Country & Sport Performance Analysis
Focuses on geographic and sport-based analysis:
- Global Medal Distribution Map
- Top Performing Countries
- Top Sports by Medals
- Country-Sport Performance Matrix

<img width="891" height="502" alt="Geographic Analysis" src="https://github.com/user-attachments/assets/b7113bea-7c13-4df4-aa39-21aac0b63c06" />

### 5. Athlete Details (Drill-Through Page)
Provides detailed athlete-level information including:
- Athlete Profile
- Olympic Participation History
- Performance Statistics
- Individual Analysis

<img width="871" height="503" alt="Athlete Detail Page" src="https://github.com/user-attachments/assets/70cb7c78-3427-4402-87e0-4e3aff625950" />

## Key Insights
### 1. Country Medal Dominance
The analysis revealed that the United States is the most successful Olympic nation, accumulating approximately 5.6K medals, significantly more than any other country in the dataset. Other strong-performing nations include the former Soviet Union (URS), Germany, Great Britain, France, and Italy. This suggests that Olympic success is heavily concentrated among a few countries that have consistently invested in athlete development, coaching programs, sports infrastructure, and long-term talent identification systems.
### 2. Top Medal-Winning Sports
The dashboard shows that Athletics generated the highest number of Olympic medals, followed by Swimming and Rowing. These sports contribute a substantial portion of total Olympic medals due to the large number of events available within each discipline. The findings indicate that countries seeking to maximize medal opportunities may benefit from prioritizing investment in sports that historically offer a greater number of medal events.
### 3. Growth of Olympic Participation
Historical trend analysis demonstrates that both athlete participation and medal counts have increased significantly over time. The number of participating athletes has grown steadily across Olympic decades, reflecting the expansion of the Olympic movement and increased global involvement. This growth highlights the increasing competitiveness of the Games and the importance of strategic athlete preparation.

### 4. Athlete Characteristics and Peak Performance Age
The Athlete Profile Analysis revealed that the majority of Olympic athletes fall within the 20–29 age group, while the average athlete age is approximately 24.45 years. This suggests that Olympic-level performance is most common during an athlete's twenties when physical fitness, endurance, and technical ability are generally at their peak. The analysis also showed variations in height, weight, and BMI across sports, emphasizing the importance of sport-specific athlete profiles.

### 5. Concentration of Olympic Success Across Countries
The geographic analysis indicates that Olympic success is not evenly distributed across participating nations. Countries such as the United States, France, Great Britain, Germany, and Italy consistently achieve strong performances across multiple Olympic Games. This pattern suggests that sustained investment in elite sports programmes, coaching quality, and athlete support systems contributes significantly to long-term Olympic success.

## Recommendations
### 1. Increase Investment in High-Performing Sports
Sports authorities should allocate more resources to disciplines such as athletics, swimming, and rowing, as these sports consistently generate the highest medal counts. Increased funding for coaching, training facilities, and athlete support programmes in these areas could improve overall Olympic performance and maximize medal opportunities.

### 2. Strengthen Youth Talent Development Programs
Since most Olympic athletes achieve peak performance between the ages of 20 and 29, sports organizations should focus on identifying and developing talent at an early age. Structured youth development pathways can help athletes gain the necessary skills and experience before reaching their prime competitive years.

### 3. Adopt Best Practices from Successful Countries
Countries seeking to improve Olympic performance should benchmark against consistently successful nations such as the United States, Great Britain, and Germany. Studying their athlete development systems, coaching structures, and performance management strategies can provide valuable insights for improving national sports programmes.

### 4. Utilize Data-Driven Athlete Profiling
Coaches and sports analysts should incorporate athlete characteristics such as age, height, weight, and BMI into talent identification and performance evaluation processes. Understanding the physical requirements of different sports can improve athlete selection and increase the likelihood of success in specific disciplines.

### 5. Implement Continuous Performance Monitoring
Organizations should adopt business intelligence tools such as Power BI to continuously monitor participation trends, medal performance, and athlete development. Real-time performance monitoring enables decision-makers to identify strengths, address weaknesses, and make evidence-based decisions that support long-term Olympic success.

## Contribution Summary
This project was completed individually. All phases of the project were carried out by the author, including:

- Dataset selection and acquisition
- Data cleaning and transformation using Power Query
- Data modeling and relationship creation
- DAX measure development
- Dashboard design and visualization
- Insight generation and business analysis
- Recommendations development
- Report writing and documentation
- Presentation preparation


### Conclusion

The Olympic Sports Performance project successfully transformed historical Olympic data into meaningful insights through interactive visualizations and analysis. The project identified key trends in athlete participation, medal performance, country rankings, and sport dominance. The findings highlight the factors associated with Olympic success and demonstrate how business intelligence tools such as Power BI can support data-driven decision-making in sports management and athlete development.




