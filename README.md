# (Airline On-Time Performance Data)
## by (Johan Coetzer)


## Dataset

> We will be using datasets which contain data about flights in the United States, including carriers, arrival and departure delays, and reasons for delays. There are multiple year's worth of data, ranging from 1987 up to 2008. This dataset also contains many different variables/columns, we will need to explore these in order to make a decision on which ones we wish to keep. We will only work with year 2007 for this analysis since it has some of the most records between all the years.
> Before we exoplored, we did some data wrangling, such as cleaning the data and fixing the datatypes.
> For the exploration, there we 3 phases, Univariate, Bivariate and Multivariate exploration.

### Univariate exploration
> Started by finding the percentage of flights that were cancelled by using a pie chart
> We then checked the amount of carrier delays by using a bar chart.
> We found which locations are the most visited by looking at the total flights to specific destinations, and sorted it in descending order to find the top 10
> Then it was explored to see which day of the weeks has the most flights by finding the value_counts() for the day of the week.
> We then explored which how long flights generally take by looking at the AirTime and grouping them into bins. We had to change the xmax limit to get a better overview of how the data is distributed.
> We explored the flight distribution across the various months by getting the value_counts() for the Month field and then sorting according to the index, so we can have the months in order.
> To get a better idea about the departure times, we made a new field from the existing departure time to only extract the hour. We then viusalized it by using value_counts() and creating a bar chart.
> To understand the flight dealys, we made a histogram using the ArrDelay field, we also needed to use xmax again to limit the x axis range.
> We explored flight diversions by getting the value_counts() of the Diverted field and plotting a pie chart.

### Bivariate exploration
> To get a better understanding of how the data is related to each other, we made a correlation heatmap using seaborne's heatmap along with the corr() method.
> We then wanted to better understand how the departure times of flights varied for different days of the week. To achieve this we made a pointplot of the departure time (hour) against the counts, with the hue set as the day of the week.
> To find the main reasons flights were cancelled, we looked at the cancellation codes for each day of the week. We created a clustered bar chart using the Days of the week with hue set as the Cancellation code.
> We also wanted to find out if there are specific weeks in which cancellation occured more often. To do this, we made another clustered bar chart with x as the DayOfTheWeek and hue being the cancelled field. This did not work so we created a heatmap instead by grouping according to DayOfTheWeek and then by cancelled.
> We also wanted to find out the cancellation ratios instead since ratios are a better measurement. To do this we created our own dataframe to store the ratios. Ratios were calculated by dividing the cancellations by the total flights for that day.
> Then we wanted to discover the destination locations which had the most cancellations. To do this, we grouped by the Destination and used the size , then sorted the values and retreived the 20 top ones.

### Multivariate
> Finally we wanted to see the Departure delays per month for each day of the week to determine if there is any changes. For this we used seaborns pointplot with x as Month, y as DepDelay and hue as DayOfWeek.


## Summary of Findings

> Only 2% of the flights listed were cancelled, meaning 98% of flights did have a lift off.
> Carrier delays are usually less than 10 minutes.
> Destinations that make up most of the flights are ATL, ORD and DFW
> The most popular days of flight is on a Monday followed by Thursdays. Saturdays are clearly the least popular days for flights.
> The peak amount of flight time is around 50-70 minutes.
> July and August seem to be the most popular months for flights
> Flights with departure in the early hours of the morning [00:00 - 04:00] are very low.
> Peak hours for flights to departure starts at 6am, and continues unitl 6pm
> Flight delays, if they occur, are usually <10 minutes.
> Flights are not diverted often, with only 0.23% of the flights being diverted.
> Strong correlations exists between CRSElapsedTime & ActualElapsedTime, CRSElapsedTime & AirTime, AirTime & ActualElapsedTime, Distance and (AirTime, CRSElapsedTime, ActualElapsedTime), ArrDelay & DepDelay
> Saturdays have the least amount of flights for all hours of the day.
> Flights are at the highest during the weekdays at 6am.
> Most popular reasons for cancellations are A (Carrier delay) for Monday to Thursday.
> Most popular reasons for cancellation for Friday to Sunday is B (Weather delay).
> Destination ORD is the destination with the most cancellations
> Saturdays have the lowest amount of departure delays across most of the months (except Jan-Mar)
> Delays are the highest for Saturdays and Sundays in December.


## Key Insights for Presentation

> I want to increase the size of some of the figures and I want to make sure the colors are uniform (although the colors are already uniform in the exploratory analysis so could potentially just be re-used.
> For the presentation I want to to show that carrier delays are usually less than 10 minutes if they do occur.
> I want to show them the most popular days for flight are on Monday and Thursday
> I want to show that flights with departure times betweeb 00:00 and 04:00 are very low and peak hours for flights are at 6am.
> Finally I want to show that most popular reasons for flight delays are carrier delays for Monday to Thurday, followed by weather for Saturday and Sunday.