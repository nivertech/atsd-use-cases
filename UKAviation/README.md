![TitlePhoto](Images/TitlePhoto.png)

Analyzing UK Aviation Statistics using CAA datasets
===================================================

### Introduction
----------------

Are airports getting more and more crowded every year?

What are the most popular travel destinations for a given airport?

Do aviation trends follow the general course of a nation's economy?

To answer such questions, the Civil Aviation Authority (CAA) serves as an independent specialist for the UK government. Established in 1972, the CAA collects and reports on key aviation metrics which summarize the level of activity at UK airports. According to their website, [caa.co.uk](https://www.caa.co.uk/Data-and-analysis/UK-aviation-market/Airports/Datasets/UK-Airport-data/Airport-data-2016-06/), the CAA collects statistics from more than 60 UK airports. Specific metrics are measured for items such as international and domestic mail shipped from UK airports (tons), international passenger traffic to UK airports, and terminal passengers at different UK airports. These reports may show the raw volumes of each metric and/or year over year (y-o-y) quarterly growth rates. 

### CAA Dataset Formats
------------------------

The datasets are available in two separate formats: raw datasets and aviation trends.

Raw datasets are published every month, and are available ranging back to 1973. From 1990 to present day these reports are available in CSV and PDF format. Datasets published before 1990 are available only in PDF format. These datasets merely contain raw data; that is they do not contain any information on analytics or trends, and do not contain any graphs or figures. These may be found at the below link:

[https://www.caa.co.uk/Data-and-analysis/UK-aviation-market/Airports/Datasets/UK-airport-data/](https://www.caa.co.uk/Data-and-analysis/UK-aviation-market/Airports/Datasets/UK-airport-data/)

Below is a dataset for "International Passenger Traffic to and from Reporting Airports (in Thousands) by Country 2005-2015," which was [published in January 2016](https://www.caa.co.uk/uploadedFiles/CAA/Content/Standard_Content/Data_and_analysis/Datasets/Airport_stats/Airport_data_2016_01/Table_11_International_Air_Pax_Traffic_to_from_UK_by_Country.pdf)

![Figure 1](Images/Figure1.png)

Aviation trends are published per quarter (four times per year). These reports date back to 2008 and are published only in PDF format. Language is used in these reports attempt to put the datasets into context. Graphs and tables showing volumes and year over year (y-o-y) growth rates of datasets are published. These may be found at the below link:

[https://www.caa.co.uk/Data-and-analysis/UK-aviation-market/Airports/Aviation-Trends/](https://www.caa.co.uk/Data-and-analysis/UK-aviation-market/Airports/Aviation-Trends/)

Below is an image of terminal passengers at UK airports from [AviationTrends_2008_Q4](https://www.caa.co.uk/uploadedFiles/CAA/Content/Standard_Content/Data_and_analysis/Analysis_reports/Aviation_trends/AviationTrends_2008_Q4.pdf). In the associated text, terminal passengers are described as "those travelers who board or disembark an aircraft on a commercial flight at a reporting UK airport." The data is presented for scheduled and chartered flights for London and Regional airports. Quantities of travelers and growth percentages are presented comparing, in this case, Q4 of 2008 to 2007, and the entire "rolling" years of Q1 through Q4 of 2007 and 2008, respectively.    

![Figure 2](Images/Figure2.png)

Below is an image from the same report showing terminal passengers at UK airports by origin / destination.

![Figure 3](Images/Figure3.png)

The data is presented for scheduled and chartered flights for passengers from within the UK, Europe, North America, and the Rest of the World. Again, quantities of travelers and growth percentages are presented comparing Q4 of 2008 to 2007, and the entire "rolling" years of Q1 through Q4 of 2007 and 2008, respectively. To summarize the graph, the following sentence is used: "Passenger numbers to all destination groups fell in quarter 4 2008, by around 8%, except for passengers numbers to the Rest of the World destination group, which fell by considerably less."

While the aviation trend PDF files can be helpful, they tend to have a very limited scope. Typically, between only 3 and 4 graphs are presented to summarize the entire quarter. To gain a meaningful understanding of the data and trends, you will need to open multiple files at a time and compare trends, which can be difficult and time consuming to work though. 

### Axibase's Time Series Database (ATSD)
-----------------------------------------

The processing of CAA datasets using Axibase's Time Series Database (ATSD) is much less cumbersome. Processing the same data with ATSD is less time consuming because the user has the ability to easily toggle between different datasets and years, and filter out for a specific airport location or metric. When loading data for a particular dataset the collector uses metadata to understand the meaning of columns and automatically extract dates, times, and categories from the data files. Besides, ATSD stores the data in the user's own database so that this public data can be combined with internal data sources as well as mixed and matched across different datasets. Once you install ATSD, you don't have to:

* Add additional datasets from caa.co.uk
* Manipulate and design table schema
* Provision an application server
* Write programs to parse and digest these types of files.

Rather, you can configure a scheduled job to retrieve the file from the specified endpoint and have ATSD parse it according to pre-defined rules. Once you have raw data in ATSD, creating and sharing reports with built-in widgets is fairly trivial. The reports will be continuously updated as new data comes in.

With ATSD, the user is able display the dataset in an easily understandable manner. Here, you can explore the complete dataset for CAA aviation statistics using our portal:

[![](Images/button.png)](https://apps.axibase.com/chartlab/972babb9)

Here, the user has the ability to filter betweeen 228 different CAA airport aviation metrics. Additionally, the user can filter between 55 different UK airports and filter by airport groups (London area, other UK, or no UK reporting airports). The figure below shows air passangers totals for 2015 for all 55 airports from January 2015 to February 2016.

![Figure 4](Images/Figure4.png)

### Creating Custom Portals
---------------------------

Custom portals can be created from the default portal. The user has the capability to change or display certain aspects of the dataset to their liking. For example, the user may change graph styling, such as color, graph type, and other display options.

Likewise, by customizing the data the way you want, you can filter out any unnecessary information. If, for example, you are interested in comparing UK Domestic terminal traffic for scheduled flights for different years, you can customize your portal from the default portal to only show that information.

The default portal, from which you can customize the dataset results, again can be found here: **[DEFAULT](https://apps.axibase.com/chartlab/972babb9)**

We will walk through a brief example on how to customize the default portal to compare UK Domestic terminal traffic for scheduled flights between 2015 and 2016. But before we walk through this example, the user must first install ATSD:

1. [Install the database](https://github.com/axibase/atsd-docs/tree/master/installation#installation) on a virtual machine or in a Linux container.
2. [Install Axibase Collector](https://github.com/axibase/axibase-collector-docs/blob/master/installation.md#axibase-collector-installation) and configure it to write data into your ATSD instance.
3. Login into your ATSD account.

### Example 1
-------------

1.  Open the default portal and delete the configuration sections as shown in the image below. We are only wanting to show one series, so there is no need for **multiple-series**, **series-limit**, **tags-dropdown**, **label-format**, **tags-dropdown-style**, or the **dropdown** control.

    ![Figure 5](Images/Figure5.png)

2.  Next, we want to select the **metric** which we would like to filter for. Once you have installed ATSD, you will want to navigate to the metric list to see the corresponding names. The first dropdown in Chart Lab contains the shortened version of the **metric** names, so you will need to log into your [https://nur.axibase.com](https://nur.axibase.com) account. The image below contains the standard view after you have logged in. Press **Entities**. 

    ![Figure 6](Images/Figure6.png)
    
3.  Enter **uk-caa** into Name Mask. Press Apply.

    ![Figure 7](Images/Figure7.png)
    
4.  Select **uk-caa**.  

    ![Figure 8](Images/Figure8.png)

5.  On the following page select **Metrics**.

    ![Figure 9](Images/Figure9.png)

6.  On the following page you will have a list of metrics, which are available for the CAA entity. In our case, we are looking for UK Domestic terminal traffic for scheduled flights. Copy the seventh entry from the top of the page, **uk-caa.air-pax-by-type-and-nat-of-op.pax_terminal_scheduled_uk**.

    ![Figure 10](Images/Figure10.png)
    
7.  Navigate back to the portal. Type in **metric=** and paste the copied metric name.  
     
