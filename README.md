# NYC-Crime-Analysis

## Task 1

1. Scrape the headlines and date of posts of 'Crime news in New York’ (or a place of your choice) spanning a few dates from a news website. 
2. Write them into a csv file 
3. Write a function called find_headline_by_keyword which lets you search through headlines for keywords and returns a list of headlines that matches the keywords
4. Use an open source sentiment analysis tool to score the sentiments of the headlines   
5. Create a time-series plot of average sentiment score against date

### Work Done

I used the website https://www.nydailynews.com to obtain news articles about crimes in the New York City area. The Beautiful Soup library was used to scrape headlines of news articles. The headlines of each article, along with the date the article was published, were stored in a CSV. Finally, I use textBlob, an open source sentiment analysis toolbox, to rate the sentiments associated with the headlines we parsed.
textBlob library returns 2 kinds of sentiment scores:

Polarity: Polarity is a float that lies between [-1,1], -1 indicates negative sentiment and +1 indicates positive sentiments.
Subjectivity: Subjectivity is also a float which lies in the range of [0,1]. Subjective sentences generally refer to personal opinion, emotion, or judgment.

A time series graph of sentiment score versus time is also plotted out!

## Task 2 (Exploratory Data Analysis)

Explore the NYPD dataset attached. Code visualizations to present crime statistics and make appropriate inferences on the data.

In this task, I look at the NYPD Crime Statistics data from the NYPD_Year_To_Date_Complaints.csv file, and try to build visualizations and make inferences about the data and crime patterns. 

### ANALYSIS IDEATION
Looking at the data, there are a variety of features, such as geographical data, temporal data, attacker and victim demographics, offence category, offence location and such.
I think each category can provide interesting insights, hence I have tried to work upon all of them, sometimes individually, sometimes in unison with other paramaters to get a better sense.

### SECTION 1: Location based Analysis
### IDEA 1.1: Distribution of crime occurrences in different areas of New York City

### Visualization tool used: Geospatial Scatter Plot

We have data about different boroughs of NYC, along with the latitude and longitude of each occurrence site. I am interested in finding out where exactly have these crimes occurred in the city, how many per borough and represent them on an actual map interface. Now since, we have over 200000 crime occurrences, representing each point on a map will not be feasible, hence I will just plot out total crime occurrences per borough.

### Insights
As we saw from the table earlier and this graph, some boroughs have a much higher crime occurrence rate than others. In this graph, different colors of labeled points show different regions and their locations around NYC. The size of the marker points correspond to the intensity of crime in the location. We can visually se that Brooklyn, Manhattan and Bronx have the highest number of crimes, followed by Queens and then Staten Island is much lower. We can conclude that the areas of Brooklyn, Manhattan and Bronx are probably the more unsafe regions in New York City, more prone to crime.

### IDEA 1.2: Distribution of crime occurrences by premise

### Visualization tool used: Pie Chart

This is a simpler visualization. The idea is to get an understanding of which places are more prone to a crime happening there. Are public or private spaces more secure? We simply count the occurrence of each premise type and visualize the top 10 highest categories.

### Insights
It can be seen from the graphs that residential apartments are the most susceptible to crimes with 31% of all crimes happening here. This is followed by the Street (public place) and residential houses/townhomes. It is an alamring fact to see that places of residence are crime hotspots. Common areas such as the departmental store, drug store, grocery or banks are relatively safer, probably because they have better surveillance options available!

### SECTION 2: Temporal (Time based) Analysis
### IDEA 2.1: Hourly distribution of crimes, split by crime category

### Visualization tool used: Multiple Bar Chart

I noticed that there is a column in the dataset showing what time of day did the crime occur. I think it could be interesting to know whether there are certain time periods within 24 hours of the day when more crimes occur? Also, there are 3 categories of crime: Violation, Misdemeanor and Felony. It could be fun to learn how these are distributed across the day too!

### Insights
This graph contains a plethora of information. First off, it can clearly be seen that misdemeanor counts (in green) are much higher than any other crime category with upto 10000 or more crimes per time block. Felony count are in the average, and violations are much lower. Coming to the hourly spread, there is a reasonably higher number of crimes after dark, in the evening, night and dawn hours, as compared to daylight hours (morning, noon). Interestingly, the maximum number of crimes are occurring in the afternoon/evening time, which makes sense as people are leaving from work and hence public spaces are crowded and residences are empty!

### IDEA 2.2: Month on month distribution of crimes committed

### Visualization tool used: Vertical Bar Chart

I wanted to check if there is any seasonality w.r.t when crimes occur more frequently during the year. The original idea was to check yearly data, but it is skewed and with an uneven distribution, hence the results were not representative. For this analysis, I extracted the month and year from the date string. Then I removed 2023 data, as it was not available for a complete year. I grouped the data by month and plotted out counts of crimes committed in each month.

### Insights
To my pleasant surprise, there is a very clearly evident trend in crimes committed per month! The number of crimes start off low at the year beginning, increases gradually and peaks substantially in the months of November and December. This has a clear correlation to holiday season, more people in public spaces, tourism season in New York City, therefore crimes would definitely shoot higher!

### SECTION 3: Demographics based Analysis
### IDEA 3.1: Demographic distribution of victims and suspects

### Visualization tool used: Tabular Representations

The dataset has columns corresponding to suspects and victims' age group, sex and race. I figure it would be intriguing to know if there are people belonging to a particular section of the population who are being attacked more, or vice versa, perpetrating more attacks! I remove 'Unknown' values from all 3 parameters and only consider semantically explainable values. I then make filter datasets for victims and suspects. Grouping is carried out based on all 3 factors together and top 10 highest contributors are represented.

### INSIGHTS
### SUSPECTS
Black men in the age of 25-44 were the most frequent offenders, with over 19000 cases, way higher than the second category: white hispanic men in the same age group (10000 cases). The number of male offenders is substantially higher than the number of female offenders. People in the age group 25-44 are most likely to be a criminal.

### VICTIMS
In the victims chart, Black Females in the age of 25-44 were subjected to the maximum number of crimes (15000), followed by Hispanic females with around 10000 attacks. The number of female victims is significantly higher than the number of male victims. People in the age group 45-64 are most likely to be attacked.

### IDEA 3.2: Distribution of Crime Activity by Offence type

### Visualization Tool Used: Donut Chart

This is a simpler visualization. The idea is to get an understanding of which types of offences are mosr prevalent. Kidnappings? Theft? Stabbing? We simply count the occurrence of each offence type and visualize the top 10 highest categories.

### Insights

It can be seen from the graphs that Petit Larceny is the most common offence type in NYC (24%). Makes sense considering the city has a lot of pickpockets! Harrassment and Assault are also pretty prevalent (21% and 14%). This is also logically sensible considering the homeless/drug addict population in the city. Burglary, Robbery or Felony Assaults are reasonably less prevalent!

Thus, I have created multiple visualizations relating to NYC Crime Statistics and derived inferences from the same. Digging into this data was an enjoyable process, it tested my skills, but I believe I have come up with a well rounded analysis piece!
