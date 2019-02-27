# FordGoBike San Francisco: User Group Analysis To Identify Growth Potential
## by Stefan Cornelißen


## Dataset

The dataset originates from FordGoBike itself and contains data of around 2.57 million rides at the moment of analysis. This amount covers the period of end June 2017 till end of January 2019. The entries / rows are described by 16 different dimensions and measures. The dataset contains "ride-related" and anonymized data only. That means, it contains no reference to the user or user ID. Therefore, the exploration is limited to the dimensions of the ride itself, which includes the following dimensions and metrics:

- Trip Duration (seconds)
- Start Time and Date
- End Time and Date
- Start Station ID
- Start Station Name
- Start Station Latitude
- Start Station Longitude
- End Station ID
- End Station Name
- End Station Latitude
- End Station Longitude
- Bike ID
- User Type (Subscriber or Customer – “Subscriber” = Member or “Customer” = Casual)
- Member Year of Birth
- Member Gender

Source and download raw data files: https://www.fordgobike.com/system-data

### Data Consistency

The value presence across the single columns is fragmented. The variable bike_share_for_all_trip has been introduced in January 2018. Furthermore, not all users have provided their year of birth or checked the value "Other" value for gender. Lastly FordGoBike introduced mid 2018 dock less bike renting as an additional service to the common station oriented renting. Data of such dockless rides are also included in the dataset. In such cases, there are no values for Start Station ID, Start Station Name, End Station ID, Ende Station Name.

All of these fragmentations are taken into account during the exploration phase, but they did not cause dedicated cleaning actions.

### Data Cleaning
Data cleaning took place along the exploration, when needed. Basically it only concerned handling outliers and NaN values. The following steps in terms of cleaning and wrangling have been undertaken:
- I added the column member_age to the column member_birth_year, by substracting the year "2019" by the birth year.
- Rows with higher values than 100 years in the column member_age have been excluded from the analysis.
- Rows with NaN values in the column member_birth_year have been excluded from the analysis.
- Rows with higher values than 4 hours (14.400 seconds) trip_duration have been excluded from the analysis.


## Summary of Findings

The here analyzed dataset from FordGoBike is based on the ride data from 28th of June 2017 till 31st of January 2019. This period is also the period of observation. The dataset has been explored by segmenting the data using the variables of user type (subscriber or regular customer), gender, age and by quantitate variables such as amount of rides and their duration.

The exploration revealed that most rides have been done by subscribers (84%). Male users account by far for the highest proportion of rides (74%). Female and male users between 25 and 34 years are the group which used the service most often. Interestingly, rides of female users were done at a younger age compared to male users. The relative distribution of rides shows a higher density around the age of thirty for woman, compared to man. Most rides took less than 40 minutes, whereas rides done by customers have a higher duration than those of subscribers. Visualizations show, that especially younger and male users show very frequent usage behavior, where older users aging between 45 and 54 years show very low usage. Furthermore, the group of female users shows overall lower usage in terms of amount of rides and total duration, compared to male users. I also  observed that the usage in terms of amount of rides and the duration do not diverge much among the segments of age group and gender. That means, the group with most rides also has the highest total ride duration. The same goes for the other segments. The highest usage is achieved by male users between 25 and 34 years. The second highest by males between 35 and 44 years.  The duration per trip (in the group of subscribers) shows that woman tend to have little longer enduring rides than man. Furthermore, rides of older users tend to endure longer than rides of younger users.

## Key Insights for Presentation

With the presentation I want to describe how user groups of FordGoBike in San Francisco are using the service. It aims to show which segments of users are using FordGoBike extensively and which are not, to identify potential for growth. The segments are defined by the member type (subscriber or cusual user), gender and age.

## Resources
https://stackoverflow.com/questions/3451111/unzipping-files-in-python
https://stackoverflow.com/questions/3207219/how-do-i-list-all-files-of-a-directory
https://stackoverflow.com/questions/39173992/drop-all-data-in-a-pandas-dataframe
https://stackoverflow.com/questions/39922986/pandas-group-by-and-sum
https://seaborn.pydata.org/generated/seaborn.heatmap.html