Project Overview: Power BI Analysis of Ola Sales, Revenue, and Customer Satisfaction


Objective

The primary goal of this Power BI project is to analyze Ola's sales performance, revenue trends, and customer satisfaction metrics. By leveraging interactive dashboards, the project provides actionable insights to enhance revenue generation, improve service quality, and address customer dissatisfaction effectively.

Key Areas of Focus

Sales Performance Analysis

Evaluate Ola's sales trends across different regions, time periods, and service types (e.g., SUV, Prime Sedan, Auto).
Identify peak and off-peak periods to optimize operational strategies.
Assess driver utilization and trip completion rates to identify operational bottlenecks.

Revenue Analysis

Monitor revenue streams segmented by geography, service type, and time periods.
Identify high-performing and underperforming areas.
Compare actual revenue against targets to evaluate business growth.

Customer Satisfaction Metrics

Analyze customer ratings and reviews to assess overall satisfaction levels.
Identify key drivers of positive customer experiences, such as ride quality, driver behavior, and app usability.
Visualize Net Promoter Score (NPS) trends to evaluate customer loyalty.

Customer Dissatisfaction Insights

Investigate the root causes of customer dissatisfaction through review and complaint analysis.
Highlight common issues such as late arrivals, pricing concerns, or app glitches.
Propose actionable recommendations to reduce complaint volumes and improve service quality.

 Tools and Technologies:

Power BI: For creating interactive visualizations, dashboards, and reports.

Data Sources: Ola's sales data, customer feedback surveys, ratings data, ride details, and regional information.

Excel/CSV: Initial data collection from multiple sources, if necessary.

SQL (if required): To answer Stakeholders Questions.
       



EXPECTED OUTCOMES/INSIGHTS
  
*RIDE VOLUME OVER TIME

*BOOKING STATUS BREAKDOWN

*TOP 5 VEHICLE TYPES BY DISTANCE

*AVERAGE CUSTOMER RATINGS BY VEHICLE TYPE

*CANCELLED RIDES REASONS

*REVENUE BY PAYMENT METHOD

*TOP 5 CUSTOMERS BY TOTAL BOOKING VALUE

*RIDE DISTANCE DISTRIBUTION

*CUSTOMER VS DRIVER RATINGS




SQL QUESTIONS:

Create database ola;
Use ola

#1. Retrieve all successful bookings:
```sql

SELECT * FROM bookings
 WHERE Booking_Status = 'Success';
```

#2. Find the average ride distance for each vehicle type:
```sql 
SELECT Vehicle_Type, AVG(Ride_Distance) as avg_distance FROM bookings  
GROUP BY Vehicle_Type;
```

#3. Get the total number of cancelled rides by customers: 
```sql
SELECT COUNT(*) FROM bookings WHERE Booking_Status = 'cancelled by Customer';
```

#4. List the top 5 customers who booked the highest number of rides
```sql
SELECT Customer_ID, COUNT(Booking_ID) as total_rides FROM bookings
 GROUP BY Customer_ID ORDER BY total_rides DESC LIMIT 5;
```

#5. Get the number of rides cancelled by drivers due to personal and car-related issues:
```sql 
SELECT COUNT(*) FROM bookings
 WHERE cancelled_Rides_by_Driver = 'Personal & Car related issue';
```

#6. Find the maximum and minimum driver ratings for Prime Sedan bookings:
```sql
 SELECT MAX(Driver_Ratings) as max_rating, MIN(Driver_Ratings) as min_rating FROM
Bookings WHERE Vehicle_Type = 'Prime Sedan';
```

#7. Retrieve all rides where payment was made using UPI: 
```sql
SELECT * FROM bookings WHERE Payment_Method = 'UPI';
```

#8. Find the average customer rating per vehicle type: 
```sql
SELECT Vehicle_Type, AVG(Customer_Rating) as avg_customer_rating FROM bookings GROUP BY Vehicle_Type;
```

#9. Calculate the total booking value of rides completed successfully: 
 ```sql
 SELECT SUM(Booking_Value) as total_successful_ride_value FROM bookings WHERE Booking_Status = 'Success';
```

#10List all incomplete rides along with the reason:
```sql
 SELECT Booking_ID, Incomplete_Rides_Reason FROM bookings 
                     WHERE Incomplete_Rides = 'Yes'; 
```



Conclusion\


This Power BI project provides a comprehensive view of Ola's business performance, combining sales and revenue analytics with customer feedback insights. The interactive dashboard helps stakeholders identify opportunities for growth, optimize service quality, and address customer pain points. By leveraging these insights, Ola can improve operational efficiency, increase customer satisfaction, and achieve sustained business success.


