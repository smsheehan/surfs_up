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



## Summary: Provide a high-level summary of the results and two additional queries that you would perform to gather more weather data for June and December.
