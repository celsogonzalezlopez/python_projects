## Overview

This dataset contains information about healthcare admissions for a hospital in India. Columns include age, gender, location, type of admission, duration of stay, and other health issues such as drinking and smoking. With this information there are many insights to be discovered and questions we can answer to understand more about the patients.

## Data Preprocessing/Cleaning

To begin, I imported pandas and read the csv file to get a look at the data. There was inconsistent formatting in the date column so I wrote a function to parse the dates. I did this so later on I can graph the number of admissions per month over time. Then, I cleaned the data by dropping the old date column in addition to renaming and lowercasing other columns.

## Exploratory Data Analysis (EDA)

With 2 years of data from April 2017 to March 2019, there were 15,757 patients admitted to the hospital. I wanted to look at the number of admissions per month over time. Using matplotlib, I plotted the line graph; the graph showed no clear trend but had peaks in November 2017 and March/December 2018. I used the describe function and saw that the average monthly admissions was 627 patients. In the lowest month it was 482 and the highest was 736. With a boxplot I noticed the Interquartile Range (the middle 50% of the data) was around 600-680 patients.

Moving on, the first question I wanted to answer was about the age demographic. The average age of all the patients was 61.43 years old. Grouping by gender I discovered that it didn’t change much: males were on average 61.72 years old and females were slightly younger at 61.25 years old. I also observed that the youngest patient admitted to this hospital was 4 years old while the oldest was 110 years old.

Next, I wanted to see if there was a difference in the number of admissions based on location. Patients at this hospital either came from rural or urban places. Overall, there were 8,397 more urban patients than rural. This suggests people there are more external factors that can cause harm or spread illness which makes sense. In urban areas there are more people that can be sick and spread it to others, more traffic that can cause accidents, more opportunities for violence/crime, etc. However, looking at the proportion of emergency patients by location it is quite similar. 67.69% of rural patients went to the hospital for an emergency. For urban patients the number is 69.83%. How I interpret this is that emergencies occur at similar rates regardless of location.

Using the duration of stay column, I discovered that emergency patients stayed at the hospital for 7 days on average. For outpatients, they stayed an average of 5.09 days; logically it makes sense that patients with more serious injuries would stay for longer. With information on alcohol use and smoking, I wanted to see if they were correlated which ended up being true. 0.29% of female patients smoke and 0.31% of them drink. 7.77% of male patients smoke and 10.04% of them drink. Males overall smoke and drink more than females but for both genders, these two activities go hand in hand.

1,105 patients died during this 2 year period. In the first year (starting April 2017), 578 died and in the second year the number was 527. Breaking down the numbers for overall deaths, we see that 827 of these patients lived in urban areas and 278 lived in rural areas. Referencing the observation earlier that there were overall more urban patients admitted, it makes sense that more of them died than rural patients. On a gender level, there were more male deaths (702) than female deaths (403) which can be attributed to several factors such as risk aversion and higher testosterone in men leading to more dangerous behaviors.

## Hypothesis Testing

Using SciPy to conduct a t-test on the data, I wanted to test whether there was a significant difference in the average stay between genders. The null hypothesis was that there is no significant difference in the average stay between males and females. The alternative hypothesis was that there is a significant difference. 

The assumptions for a t-test are normality and homogeneity of variances. I tested normality with the Shapiro-Wilk test and homogeneity of variances with Levene's test. Then I continued on with the t-test and the p-value was less than 0.05 so I rejected the null hypothesis and concluded that there was a significant difference in the average stay between males and females. I calculated this and it turns out females stay on average 4.8 hours longer than males.
