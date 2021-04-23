# Fordgobike_Data_Exploration
## by Meng Tan


## Dataset

This dataset containing the whole year (2019) information about approximately 2,506,983 individual rides made in a bike-sharing system in the greater San Francisco Bay area. The information included ride duration time, ride start time, end time, user type, start station longitude and latitude, end station longitude and latitude, and some other attributes. I collected these 12 months' data from [LWFT Website](https://www.lyft.com/bikes/bay-wheels). Since some months' datasets did not include columns `bike_share_for_all_trip` and `rental_access_method`, I decided to remove these two columns from other months and combined all months into a whole year data. After cleaning process, I removed one outlier for an impossible duration time and 103 observations for test purpose.

This is a direct url to [Data Source](https://s3.amazonaws.com/baywheels-data/index.html).

## Summary of Findings

In the bivariate exploration part, I found that ride demands happened in three geologically separate regions, while after exploring further with another variable user_type, I discovered that subscribers dominated area A and B, but only dominated the centre of area C. For area C, relatively more customers appeared in periphery of C. Then after comparing separately the change through months for these three regions, it suggests that there's a generally spreading tendency from January to July for all regions, and rides cover more area in July and December for A and C.

Comparing duration minutes per ride, I found that customers tend to ride longer than subscribers for time of a day, day of a week, and month of a year.

Taking both the number of rides and duration minutes per ride into account, I chose to use total duration minutes of a whole year as riding demand metric. Then I found that the northeast of area A achieved the highest total bike duration time among three areas. For the relationship between year duration minutes with different time on different days of a week, I discovered that weekdays achieved more duration time than weekends, and there are total different peak periods between weekdays and weekends. After adding the influence of user types, I found that customers contribute relatively more to the weekends compared to weekdays, while subscribers contribute inversely.


## Key Insights for Presentation

Since my interest is to explore ride demands from this dataset, I considered the number of ride, duration time per ride, and total duration time as metrics for ride demands. Therefore, my presentation mainly focuses on the relationships between variables of interest and these three metrics.

I start by introducing the distribution of duration time per ride, followed by the pattern in longitude and latitude distributions, then plot the scatterplot of longitude and duration time per ride with logarithmic transformation.

Next, I introduce the patterns for user types with pairs of three categorical time features (time of a day, day of a week, and months) related to the number of rides.

Since it is more intuitive to get the idea of ride demands from the images of rides spreading geologically, I present the distribution of customers and subscribers with consideration of longitude and latitude. To dig it deeper, the changes along months of a year are also showed for three regions.

Afterwards, I use point plots to introduce the patterns related to duration time per ride considering the three time features and user types.

Finally, the distribution of total duration time for a year are presented with geological coordinates(using 2D histogram plot), with hours and days of a week, and with user types(using heatmaps).

**The commend for creating a slide deck with Jupyter in terminal:**
`jupyter nbconvert ford_gobike_slides.ipynb --to slides --post serve --no-input --no-prompt`
