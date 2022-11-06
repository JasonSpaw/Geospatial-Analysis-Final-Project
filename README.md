# Geospatial-Analysis-Final-Project
Final Project submitted for Geospatial Analysis Course. 

- Roughly 1 in 107, people die in car crashes every year.  The purpose of this story is to uncover what may be some contributing factors to car wrecks as to spread awareness.

- My sources of data can be found at these links.
  - https://www.ariesportal.com/Downloads/Download?icon=fa-download
  - https://hub.mph.in.gov/dataset/aries-crash-data-2007-2017
  - https://www.fhwa.dot.gov/policyinformation/hpms/fieldmanual

- The audience I wish to reach are those curious about what might be contribute to roadway accidents.

- For this project 3 grids, at varying resolutions for grid size (1K, 2K, 3K), were utilized to observe the effects of MAUP (Modifiable Areal Unit Problem) for analysis. The concentrations of crashes, road miles, annual average daily traffic (AADT), and various types of intersections,  along with the average speed limit, were aggregated to the grid cells for further use.
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/Crash%20Grid%201.png)
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/Crash%20Grid%202.png)
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/Crash%20Grid%203.png)
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/Roads%20Grid%201.png)
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/Roads%20Grid%202.png)
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/Roads%20Grid%203.png)

- Analysis 1
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/Speed%20limit%20ranges.png)
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/crashes%20over%20speed%20limit.png)
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/crashes%20per%20mile%20v%20speed%20limit.png)

- This analysis is to look at the relationship between speed limit and vehicle crashes on roads.  When observing the map with crashpoints in relation to road speed limits, there does appear to be a correlation between speed limit and crashpoint frequencies. However, when observing the bargraph of crashpoint frequencies per speed limit, it becomes clear that the correlation is more likely due to the geographies and traffic conditions of where the speed limits are posted, rather than speed itself.  Higher crash frequencies are seen in areas where the speed limit is either zero or between 30 and 55 miles per hour.  This seems to indicate that vehicle crashes are more prevolent in areas of higher congestion or possibly where more attention to surroundings is needed.  Areas that have a speed limit of zero are likely residential areas where no speed limit is posted, where although drivers will likely not be driving as fast as the highway, crashes may result more from lack of caution for a lot more obsticles that may arise, such as pedestrians or other vehicles pulling out of driveways.

- Analysis 2
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/AADT%20quantiles.png)
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/Crashes%20Over%20AADT.png)
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/Crashes%20per%20mile%20v%20AADT.png)

- This analysis is to look at the relationship between the Annual Average Daily Traffic (AADT) and vehicle crashes on roads.  When observing the map with crashpoints in relation to road AADTs, there does appear to be a correlation between AADTs and crashpoint frequencies. However, when observing the bargraph of crashpoint frequencies per AADT bins, it becomes clear that the correlation is more likely due to the geographies and traffic conditions, rather than AADT of the road segment.  When observing the bargraph of crashpoints per mile in relation to the AADT of roads, it becomes clear that the crash frequency might likely be more of a result geographies and traffic conditions of that length of road.  Roads in residential and shopping areas would see a consistent flow of traffic but yet not as much traffic as major highways.  Thus, clustering within regions of AADT levels is observed much like with speed limits and crash frequencies drop off at higher AADT, where drivers are on the highways and, although they are traveling much faster speeds with a higher volume of other vehicles, need to focus on less potential risks and simply focus on staying in their lane until they need to take the exit ramp, which still would likely require attention to fewer potential risks than if driving in residential or shopping (urban) areas, where there are more obsticles and turns to pay attention to.

- Analysis 3
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/model1.PNG)
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/model2.PNG)
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/model3.PNG)
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/model4.PNG)
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/model5.PNG)
![](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/model6.PNG)

- This analysis is to observe a linear regrssion fit between crashpoint frequencies and potential factors of vehicle crashes.  The first three set of models look at linear regression models fitted across polygons of the three varying grid resolutions, with speed limit and AADT kept as features.  Models 4,5, and 6 were fitted across the same grid resolutions respectively but without speed limit and AADT as features.  The coefficient for intersections with traffic light signals was positvie in all model fits, showing a clear correlation to those particular types of intersections while other intersections had negative coefficients.  "TotalRoadMiles" and "AADT_density" also had positive coefficients in each model showing a positive corelation to "CrashesPerPolygon".  Models where speed limit and AADT were retained performed better overall, meaning that although my previous analysis led me to believe that these factors were likely not directly correlated, they are likely still correlated indirectly through other underlying factors and, therefore, both "Avg_Speed" and "AADT_density" should be retained and factor analysis of the variables should be explored to improve the fitting of the regression models.

Overall, the regression models do prove to be a viable predictor model for "CrashesPerPolygon" in these datasets, with increasing accuracy as the resolution of the polygon grids is increased, based off the results of R-squred.  However, a much more in depth analysis would be required for better fitting.

- [Code here](https://github.com/JasonSpaw/Geospatial-Analysis-Final-Project/blob/main/Project-GeospatialWorkflow!.ipynb)
