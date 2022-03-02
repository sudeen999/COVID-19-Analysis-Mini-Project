# COVID-19-Analysis-Mini-Project

OBJECTIVE:
Our goal through this project is to use the data in a practical setting, perform some manipulations on the data and gain insights from it. We have created interactive dashboards tracking the number of cases, deaths, and recoveries – by country, based on the publicly available COVID-19 dataset provided by Johns Hopkins University and another dashboard tracking the cases in India, state-wise.

Steps Followed:
1. DATA GATHERING
The dataset has been collected from the GitHub data repository operated by the Johns Hopkins University, Centre for Systems Science and Engineering (JHU CSSE). We have taken three datasets which have a record of a cumulative number of ‘Confirmed cases’, ‘Recovered cases’ and ‘Deaths’ on each date starting from 22nd January 2020 to up until the day before, i.e., here, we are working on real time data. So, the data that we are working on comes under the ‘Time Series’ data, i.e., collection of data at regular intervals in terms of days, hours, months and so on. Each dataset consists of columns, namely, Country, Province/State, Latitude, Longitude and all the dates. In total, each of the three datasets have 350 columns (i.e., before transforming the data).Each of the three datasets consists of approximately 250-300 row entries before data cleaning and transformation.


2. DATA PROCESSING
The process of removing/modifying data that is incorrect, incomplete, unrelated, repeated or not formatted properly, in order to perform further analysis. Firstly, we use the isnull() function to check for any null values in each of the datasets.


3. DATA TRANSFORMATION
After cleaning the data, the next step is transforming our data into a desired format. By definition, data transformation is the process of converting data from one format or structure into another format or structure. In our datasets, the dates are in the form of columns. For the purpose of calculating the confirmed cases, recovered cases and deaths on a daily basis, we need to transform the date columns into row entries, or so to say, unpivot the date columns. For that, we use the melt() function in pandas. In the code given below, we write the names of the columns that we want to fix in ‘id_vars’ and rest of the columns then get unpivoted.


4. DATA MERGING
Further, we join the three datasets into a single dataset so that it’s easier to work with. We use the merge() function on the ‘Confirmed cases’ dataset and the ‘Deaths’ dataset and merge them together into a single dataset. Next, we merge that dataset with the ‘Recovered cases’ dataset. Finally, we have all the three datasets merged into a single dataset.


Next, we perform some calculations on our data to derive the daily numbers from the cumulative numbers. Fundamentally, we subtract the total no. of cases on a particular day from the total no. of cases recorded on the next consecutive day, which gives us the daily records that we would want.
Now that our dataset is in perfect condition for further analysis after we have cleaned and transformed it, we export the transformed data to an Excel file and import it into Power BI for data visualization.
