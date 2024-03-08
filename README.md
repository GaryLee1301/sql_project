## Chicago Taxi Project

### **Project Overview**
A small project that I am working on to showcase what I have learned.

The original data that I used can be found within [Big Query](https://console.cloud.google.com/marketplace/product/city-of-chicago-public-data/chicago-taxi-trips?q=search&referrer=search&project=sql-demonstration-416514)


### **Tools that I used**
- Excel
- Big Query
- Tableau

 ### **Data cleaning/preparation**
 I checked the data and noticed that some location was redacted due to privacy concerns.
 I removed those columns from the table, and saved the new query for further handling.
 These are the codes that I used
  ```sql
  SELECT  * EXCEPT (pickup_census_tract,
  dropoff_census_tract,
  pickup_community_area,
  dropoff_community_area,
  pickup_latitude,
  pickup_longitude,
  pickup_location,
  dropoff_latitude,
  dropoff_location,
  dropoff_longitude)
  FROM 'bigquery-public-data.chicago_taxi_trips.taxi_trips'
  ```

We can then save the new query as a BigQuery table, and it should bring you to a new console page with the saved result.



### **Data analysis**
I checked to see if longer trips tend to receive a bigger amount of tips by using this code here.
  ```sql
  SELECT tips, trip_seconds
  FROM `sql-demonstration-416514.chicago_taxi_cleaned.Chicago taxi`
  ORDER BY trip_second DESC
  ```


I repeated the steps to check if distances made an impact on how passenger tips as well.
```sql
SELECT tips, trip_miles
FROM  `sql-demonstration-416514.chicago_taxi_cleaned.Chicago taxi`
ORDER BY trip_miles DESC
  ```


### **Results/Findings**
1. The revenue for the taxi industry in Chicagois facing a decline since 2015 ![image](https://github.com/GaryLee1301/sql_project/assets/162598482/dde1363f-324e-45c6-b8b2-3cacd70d8246)


2. People tend to tip more if they are using the taxi services for a longer ride/ distance.![image](https://github.com/GaryLee1301/sql_project/assets/162598482/eef76366-1e23-40a0-b525-27ac7712b0b1)

3. People tend to use taxi services the closer it gets to weekends.

   ![image](https://github.com/GaryLee1301/sql_project/assets/162598482/832b4ba8-3488-4f03-9447-050d66199635)

3. Although the overall revenue for the industry is decreasing, the average fare have increased over the years.![image](https://github.com/GaryLee1301/sql_project/assets/162598482/d8c4def1-4395-48e0-8d01-577e2e55564e)



### **Recommendations**
- Dynamic Pricing Strategy:
  - Implement a dynamic pricing strategy based on demand, time of day, and special events. This can maximize revenue during peak hours and high-demand periods.
- Partnerships and Alliances:
  - Explore strategic partnerships with businesses, events, or local establishments to offer exclusive deals or discounts. This can broaden our customer base and attract new riders.
- Feedback Mechanism:
  - Establish a robust feedback mechanism to collect customer opinions and suggestions. Use this information to address pain points, improve services, and foster a stronger connection with our clientele.
 
### **Limitations**
The data that I was able to download was limited as the file size that I can download from BigQuery is limited. 
The purpose of this project is to showcase the skills that I have picked up and will use in a real environment.

### **References**
Link to my visualization on [Tableau](https://public.tableau.com/app/profile/gary.lee5972/viz/Chicagotaxiproject/Dashboard1#1)
