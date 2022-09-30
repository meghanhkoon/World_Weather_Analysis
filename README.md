# World Weather Analysis

## Overview

***Background***

As a new employee as a data analyst at Pyber, a Python-based ridesharing app company, we first did an exploratory analysis on two large CSV files. We created different graphs (line, bar, scatter, bubble) using the Matplotlib library in Jupyter Notebook. We were able to create analysis to help Pyber improve ridesharing access to underserved neighborhoods. We specifically look at the data from the three different city types: Urban, Suburban, and Rural. 

***Purpose***

After the exploratory analysis of Pyber's data, the purpose of our new assignment is to create a summary DataFrame of ridesharing by data type. Then, we were tasked with using Pandas and Matplotlib to create a multiple line graph that demonstrates the total weekly fares for each city type (Urban, Suburban, and Rural). From the data summary, graphs, and visualizations, we will report our findings to PyBer. 


## Resources 
- Data Source: 
- Software: Python 3.9.12, Anaconda 4.14.0, Jupyter Notebook 6.4.8 , Pandas 1.4.2 , Matplotlib 3.5.1


## Results: Statistics & Analysis


### Summary Statistics 
Before creating a summary table, two csv files (ride_data.csv and city_data.csv) had to be read, converted into DataFrames, and merged. Then the groupby() and count()/ sum() functions were used to find the necessary information. To find Average Fare per Ride, we divided the number of rides by total fares. Lastly, to find the Average Fare per Driver, we divided the Total Drivers by Total Fares for each city type. See the Pyber summary DataFrame organized by type of city (Rural, Suburban, and Urban) below:  

![Pyber_summary](analysis/Pyber_summary.png)

From this table, we can assume: 
1. The Urban city type had more total rides, drivers, and fares than Rural and Suburban cities. We see that Urban cities bring in more revenue than the other two types of cities. 
2. The Average Fare per Driver is three times higher in Rural cities vs. Urban cities. This means that drivers make more money for PyBer in Rural areas vs. Urban and Suburban cities. PyBer could make more revenue if they provided/ had a bigger need for ridesharing in Rural areas. 
3. Surprisingly, we see that within the Urban city type,  there were more drivers (2,405) than rides (1,625). This may be why the Average Fare per Driver for Urban was significantly lower ($16.57) in Urban cities vs. Rural ($55.49) and Suburban cities ($39.50).


### Visualization Analysis
After creating a summary table, we then continued our analysis by creating a multiple-line graph that shows the total fares for each week by city type. To do this, we grouped our merged data frame by "type," "date," and the sum of the "fare." To use the date column, we had to reset the index to first create a pivot table of our grouped information. Then we used the loc() function to find the fares from '2019-01-01':'2019-04-28' (January 2019 to April 2019). Next, we had to change the index type to datetime so our last resample() function would work. We used the resample() function to find the sum of the fares per week. 

![PyBer_fare_summary](analysis/PyBer_fare_summary.png)

From this graph, we can assume: 
1. During the months of January to April in 2019, we see that Urban cities consistently had the highest total fare and Rural cities had the lowest. 
2. In the third week of February, all city types (Urban, Suburban and Rural) had their highest total fares during the months of January to April. 
3. After the peak at the end of February, Urban cities total fares' peak goes up and down throughout the month of March then taper off through April. Suburban cities total fares plateau through March, takes a slight dip in the beginning of April, and starts to increase through the month of April. Lastly, Rural cities continue to plateau throughout March and April with a peak in fares at the beginning of April.

## Summary
After our initial exploratory analysis and specified analysis of the three types of cities, our recommendations for PyBer are as follows: 

1. With Urban cities having the highest total fares and amounts of rides, we can assume that Urban cities bring PyBer the most revenue. We also see that within Urban cities, there is two times the amount of drivers than riders. PyBer could consider focusing on marketing/ advertising in Urban city types to increase the demand for rides (without losing Urban drivers). 
2. Although Rural cities make the least profit in fares and amounts of rides, the average fare per ride is the highest (almost three times the amount of Urban's fares).  We also know that drivers make the most in this type of city. If there could be a little more marketing towards hiring more drivers, we could possibly see an increase of ridership within this type of city. With increasing the supply (more drivers) in Rural cities, it could significantly increase the company's overall revenue.
3. Lastly, looking at the Total Fare by City Type over the span of January to April, we see that all three types of cities have their highest total fares peak in the third week of February. If the company could further investigate what caused this peak, they could use this valuable information and apply it to all cities to help further the company's success over time. 




