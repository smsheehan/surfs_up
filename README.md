# surfs_up

## Overview of the analysis: Explain the purpose of this analysis.

The purpose of this analysis is to dive more deeply into the weather data, specifically on temperature trends, to inform whether or not opening a surf and ice cream shop in Oahu is a good idea. This analysis looks at temperature trends during two months, June and December, to inform whether the surf and ice cream shop business will be sustainable year-round. From a skills standpoint, this challenge tests our ability to use sqlalchemy to query the database, convert the relevant data into a dataframe and obtain summary statistics.


## Results: Provide a bulleted list with three major points from the two analysis deliverables. Use images as support where needed.

The summary statistics for June were obtained with the below code to query the database.  

![image](https://user-images.githubusercontent.com/90977689/142477056-e292d0de-ba37-4d51-a2a3-04ce8825e6e7.png)

the June temperatures were then converted to a list using np.ravel() and then converted to a dataframe.  After renaming the temp column to "June Temps", the resultant summary statistics are as follows:

![image](https://user-images.githubusercontent.com/90977689/142477882-228107fc-d3b8-4f82-b83e-8d752ff1b49c.png)

The December analysis was done in similar fashion, changing the month filter from "6" to "12" in the initial database query.  The resultant summary statistics for December are as follows:

![image](https://user-images.githubusercontent.com/90977689/142478171-28d133b3-35ac-4ef5-917e-01144f25501a.png)

Three main points from comparing the two analyses:
* The mean temperature difference between June and December is only 4 degrees, going from a mean of 75 in June to a mean of 71 in December.  This indicates that the shop would be located in an area that has year-round temps that are suitable for surfing.
* The minimum recorded temperature in December was 56 degrees, while the minimum recorded temperature in June was 64.  This indicates that there will be some chilly days in December where business might be slower.  It might be worthwhile to make sure the shop is well stocked with wet suits in December and perhaps make plans to sell some hot beverages to offset the expected decrease in ice cream sales. See the summary section for additional queries related to this.
* The June data is a little tighter than the December data.  June is based upon a higher number of data points (June 2017 is included in the data set), has a smaller delta between max and min temps, and a smaller standard deviation.  December data for 2017 wasn't available in the database so the December data is based on 7 years worth of recorded data.  The december standard deviation is higher than June, so we can expect December to be a little more hit or miss with respect to temperature relative to the mean.  We should dive into the December data in more detail.

## Summary: Provide a high-level summary of the results and two additional queries that you would perform to gather more weather data for June and December.

At a high level, the data confirms there is opportunity for sales of both surf supplies and ice cream throughout the year.  However, it can be expected that there will be a sales dip in December based on the temperature trends revealed in the analysis.  There are some additional queries we can perform to better understand the December data.
* First:  are we missing anything by looking at all seven years of data at once?  Is the median temperature wildly different from year to year?  We can probe this with the following code:

![image](https://user-images.githubusercontent.com/90977689/142726196-7f17fe21-4b18-4293-a318-bdb9643adb85.png)

    
What we see is that the mean temperature remains pretty consistent from year to year.  While 2015 was warmer than usual, all of the other years fall roughly within two degrees of the mean temperature we obtained from the combined analysis.
    
* Second:  Since temperature isn't the only deciding factor for business, I am curious as to how precipitation might play a role in how we think about December's business.  To test my approach, I arbitrarily decided that days where rainfall was >= 0.5" or days were the temperature was below 65 degree represented scenarios, or crummy days, where we are not likely to get a lot of business.  I probed this with the following code which filtered on either of the two weather occurences.

![image](https://user-images.githubusercontent.com/90977689/142726567-59cef1dd-6b2e-4f94-b851-a843b25fb1cd.png)


This shows us that we can expect a decent number of crummy days in December.  While 2014 was almost a complete washout with respect to number of crummy weather days, we should plan for at least one third of December to have days with low sales.   Understanding business trends relative to temperature and precipitation would help us arrive at perhaps more informed cutoffs for temperature and rainfall amounts for defining crummy days in a future query.  We may want to stock umbrellas and offer warm beverages in December to try to offset decreased surfboard and ice cream sales.





