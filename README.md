# Ford GoBike System Data
## by Anzela Minosi


## Dataset

> The data consists of more than 2.5 million trips taken by shared 
bikes, including start  hour, start weekday, start month, station ids, 
customer types and other qualities related to a bike sharing system in a large 
city. The dataset for the San Francisco Bay area can be found 
[here](https://s3.amazonaws.com/fordgobike-data/index.html), with feature 
documentation available 
[here](https://github.com/BetaNYC/Bike-Share-Data-Best-Practices/wiki/Bike-Share-Data-Systems).
The cleaned dataframe can be [downloaded here](https://drive.google.com/file/d/1TXScz-T3zqbCyYtw2IcRNmMW-PnGdZNa/view?usp=sharing).

> As I wanted to cover a full year with analysis, I downloaded 17 .csv files 
which were merged into one large .csv file. After having assessed the dataset 
visually and programmatically, I decided that I needed to perform some data 
wrangling in order to use it for my analysis. As a result, I converted the 
features birth years, and station ids from float to int. However, I had to drop the 
rows where these columns contained null values. Additionally I wanted to 
investigate the time feature, so I converted the start and end time columns to 
datetime. Then I created addititional columns `start_month`, `start_weekday`, 
and `start_hour` which stored corresponding values that were extracted from the 
`start_time` feature. Two further columns `start_weekday_name` and 
`start_month_name` were created that stored not the corresponding numbers of 
the weekdays and months but their names. What's more, I created the column 
`difference_station` which stored the result of the calculation 
`start_station_id` - `end_station_id`. 


## Summary of Findings

> In the exploration, I found that there was a strong relationship between the 
duration in seconds and the difference in station ids, start station ids and 
the year of birth of the members. A smaller difference in station ids was 
usually associated with a longer duration in seconds. The same was true when 
looking at start station ids. Additionally, the year of birth of the customers 
showed a strong logarithmic effect on the duration in seconds. In general, 
younger customers tended to rent a bike for a longer period of time.

> When investigating the start time together with the customer type, I found 
out that (irregular) customers rented a bike for a much longer period of time 
on average compared to subscribers. What's more, the relationship between the 
start weekday and the station id showed that on weekends the distribution 
between the station ids is more balanced compared to workdays where mostly the 
smaller station ids are well frequented.


## Key Insights for Presentation

> For the presentation, I focus on what influence the start time, the 
customers  as well as the station ids will have on the duration of a trip and
leave out the other variables. I start by introducing the duration variable, 
followed by the start time variable which will be depicted as a distribution of 
hour, then plot the transformed heatplot. 

> Afterwards, I introduce the station id variable. To start,
I'm plotting a two dimensional histogram which shows the effect of the 
difference in stations on the duration. 

> Another main categorical variable will be the weekday which will be
presented by a distribution plot followed by showing its influence on the 
stations.

> The last main categorical variable will be the user type which will be
presented by showing its influence on the duration, start hour, start station
id, and the weekdays. These plots will depict multivariate
distributions.
