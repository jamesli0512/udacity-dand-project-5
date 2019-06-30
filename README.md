# udacity-dand-project-5
# Ford GoBike Communicating Data Findings Project
## by Haotongli
## June 29 2019


## Dataset
### Structure of dataset

The original Bay Wheels's trip dataset contains 2114592 rides and 16 features. I added 7 more features for analysis purpose. 

01. **`duration_sec`**: Trip Duration (seconds)
02. **`start_time`**>: Start Time and Date
03. **`end_time`**: End Time and Date
04. **`start_station_id`**: Start Station ID
05. **`start_station_name`**: Start Station Name
06. **`start_station_latitude`**: Start Station Latitude
07. **`start_station_longitude`**: Start Station Longitude
08. **`end_station_id`**: End Station ID
09. **`end_station_name`**: End Station Name
10. **`end_station_latitude`**: End Station Latitude
11. **`end_station_longitude`**: End Station Longitude
12. **`bike_id`**: Bike ID
13. **`user_type`**: User Type (Subscriber or Customer – “Subscriber” = Member or “Customer” = Casual)
14. **`member_birth_year`**: Member Year of Birth
15. **`member_gender`**: Member Gender
16. **`bike_share_for_all_trip`**: Boolean to track members who are enrolled in the "Bike Share for All" program for low-income residents
17. **`start_metro_area`** <u>[added feature]</u>: Starting station's metro area
18. **`end_metro_area`** <u>[added feature]</u>: Ending station's metro area
19. **`member_age`** <u>[added feature]</u>: Age of user
20. **`age_group`** <u>[added feature]</u>: Age group of user
21. **`month`** <u>[added feature]</u>: Month of ride
22. **`weekday`** <u>[added feature]</u>: Day of week of ride
23. **`hours`** <u>[added feature]</u>: Time of day of ride

### Accessing Summary

01. **`start_station_id`, `start_station_name`, `end_station_id`, `end_station_name`, `member_birth_year`** and **`member_gender`** columns have missing values
    <br>1.1. **`start_metro_area`** and **`end_metro_area`** columns should be added to label strat and end stations
02. **`start_time`** and **`end_time`** should be data type datetime
03. **`weekday`** and **`hours`** column should be added for analysis
04. **`start_station_id`, `end_station_id`, `member_birth_year`** should be data type int
05. **`member_birth_year`** should be converted to member's age 
    <br>5.1. **`member_age`** outliers should be removed
    <br>5.2. **`age_group`** column added
06. **`bike_share_for_all_trip`** should be boolean
07. **`user_type`**, **`member_gender`**, **`month`**, **`weekday`** and **`hour`** should be categorical variables
08. **`duration_sec`** has many large values maybe outlier due to customers forgot to log off after using

## Summary of Findings

> Most bike riding activities happened in **San Francisco area**. This is make sense because SF is the first location of GoBike. Among the **2114592** bike activity in df_clean, only **65 inter-area rides**.
> All of the rides are between SF and oakland across the Bay Bridge and **58 trips (~90%)** are from subscribers.
> From **`duration`**, **`member_age`** vs.  **`user_gender`**, **`metro_area`** by **`user_type`** graph, several conclusion can be made:
01. **Subscribers** have **shorter and more concentrated duration range** than **Customers**
02. **San Jose's Subscriber** population is the **youngest**
03. **East Bay's Subscriber** have the **shortest duration**
> Majority of users is from **age groups 20s and 30s**. Although San Francisco metro area has most rides but the two largest user populations 20s and 30s age groups have the **lowest subscription ratio**.
> **San Jose**, as the last area of GoBike started operation, has the **lowest total number of rides for each month**. However, it has the **highest user's subscription ratios for each month**.
> **San Jose**'s hourly distribution **does not exhibits the "2 peaks" pattern** as San Francisco and East Bay. Usages from **8am to 3pm** is rather **flat**. I think the reason behind is the flexible working hours for companies in the San Jose area, people don't have to follow the 9am-to-5pm work schedule.


## Key Insights for Presentation

> **Subscriber**'s most frequently used time is **weekday around 7-9am and 4-6pm**, which are the commute times. **Customer**'s most frequently used time, beside the commute times, is **weekend 12pm-4pm**. <br>
> **Subscribers** use the bike mostly for commute to work. **Customers** use the bike during weekend for leisure.
