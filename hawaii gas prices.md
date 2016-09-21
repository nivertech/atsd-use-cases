Pain at the Pump - a Closer Look at Hawaii's High Gas Prices yyyyyyyy
=============================================================

Hawaii. Sunshine. Beautiful beaches. Piñas coladas. These are a few of the great motivators for moving to one of America's favorite vacation destinations. However,
Hawaii has some of the most expensive consumer products in the nation. According to [expastistan.com](https://www.expatistan.com/cost-of-living/comparison/new-york-city/honolulu), 
in comparision to New York City, considered one of the most expensive cities in the world, Honolulu is more expensive by the following percentages:

* 1 liter of whole fat milk: 41%
* 1 kg(2 lbs) of apples: 68%
* Bread for 2 people for 1 day: 67%
* 1 liter (1/4 gallon) gasoline: 12%

Hawaii, according to [gasbuddy.com](https://www.gasbuddy.com/USA), has the highest gas prices in the entire United States. In order to help better analyze this and other data over time, the
US government has established a data collection website, [data.gov](https://www.data.gov/), Data is available to conduct research, develop web applications, and design data visualizations,
on a variety of topics ranging from agriculture, to manufacturing, to health. Data can be downloaded as a CSV, RDF, JSON, or a XML file. To help interpret this
data, the user is given the option of opening the CSV file with either [CartoDB](https://carto.com/) or [plotly](https://plot.ly/). In this instance, the user is given information on the each of the
following locations: 

* Hilo
* Honolulu
* Wailuku
* US
* State of Hawaii

For each location, data is provided for Diesel, Gasoline - Regular, Gasoline - Midgrade, and Gasoline - Premium. CartoDB is primarily a mapping software and does
not allow the user to plot the data set (in this case gas prices of Hawaii) over time. plotly fairly allows the user to display the relationship of gas prices over 
time; however, without manipulating the raw data set, each location is allowed to be compared with only one fuel type at a time. Once the raw data is pulled
into plotly, the user must select Filter from Data Tools (as shown in Figure 1). Next, the user must sort by Fuel (as shown in Figure 2). 

![Figure 1](Filter.png)  ![Figure 2](Filter 2.png)

Finally, to output the data, the user must select Group By and choose Month_of_Price as the x axis, County as G (this will seperate the prices of fuel for each 
location), and the Price as the y axis (Figure 3).

![Figure 3](Filter 3.png) 

The ouput will look as is shown in Figure 4.

![Figure 4](Gasoline Regular.png)

The processing of data with Axibase's Time Series Database (ATSD) is much less cubersome. With ATSD you don't have to stage a database, manipulate and design
table schema, provision an application server, and write programs to parse and digest these types of files. Rather, you can configure a scheduled job to retrieve
the file from the specfied endpoint and have ATSD parse it according to pre-defined rules. Once you have raw data in ATSD, creating and sharing reports with
built-in widgets is fairly trivial. The reports will be continuously updated as new data comes in.

With ATSD, the user is able display the data in an easily understandable manner. Figure 5 shows each fuel type for each of the 5 locations.

![Figure 5](.png) 

The Dataset can be sorted by location and/or fuel type, and the user can easily toggle through comparing different scenarios. Figure 6 and 7 show outputs
comparing fuel types on Hilo and Diesel prices by location, respectively.

![Figure 6](.png)

![Figure 7](.png)

The Dataset can also be manipulated to show price differences for different fuel types, for example for diesel between Hawaii and the US (Figure 8)

![Figure 8](.png)



  





     
