__Seafood Restaurants in Boston Neighborhoods__

Sujit Kandar, 06-24-2021


__Contents:__
1. Introduction/Business Problem
2. Description of the Data
3. Methodology
4. Results
5. Conclusions
6. Acknowledgement






__Introduction/Business Problem__

The city of Boston is truly a multicultural and diverse city in the United States. It has a lot to offer: rich history, culture, sports, higher education, healthcare, and of course the fresh sea foods. Millions of visitors from all over the world visit Boston every year and many of them crave for Boston’s famous seafood. Locally harvested lobsters, oysters, cod, tuna, and many other species provide a plethora of options to choose from. 

In this project I wanted to provide a simple recommendation system to the visitors to choose a Boston neighborhood with the highest concentration of seafood restaurants so that they will have many options to choose from. It will provide visual locations of the restaurants in the map which can be zoomed in or out to help planning a better visit. 


__Description of the Data__

For this project, I scraped the Boston neighborhoods data from Wikipedia (Neighborhoods in Boston - Wikipedia) using the Beautiful Soup library and I obtained the restaurant information in Boston neighborhoods from Foursquare using an API. These two sets of data were merged, a cluster analysis was performed by the k nearest neighbors regression method followed by the creation of a geographical map using folium library.


__3. Methodology__

3.1. The get request and beautiful soup object was created to fetch the neighborhood data from wikipedia.

3.2. The neighborhood data was stored in the "boston_neighborhoods" list.

['Allston',
 'Back Bay',
 'Bay Village',
 'Beacon Hill',
 'Brighton',
 'Charlestown',
 'Chinatown–Leather District',
 'Dorchester (divided for planning purposes into Mid-Dorchester and Dorchester)',
 'Downtown',
 'East Boston',
 'Fenway-Kenmore (includes Longwood)',
 'Hyde Park',
 'Jamaica Plain',
 'Mattapan',
 'Mission Hill',
 'North End',
 'Roslindale',
 'Roxbury',
 'South Boston',
 'South End',
 'West End',
 'West Roxbury',
 'Wharf District']

3.3. A pandas data frame was created from the "boston_neighborhoods" list.

3.4. A function was created and called upon the neighborhoods to get their latitude and longitude coordinates.

3.5. The coordinates were converted into a pandas data frame from the list.

3.6. Coordinates of Boston were retrieved using geocoder library and a map of Boston along with the neighborhoods will be created using folium library.

The geograpical coordinate of Boston, Massachusetts 42.3602534, -71.0582912.



3.7. Boston neighborhoods venues were explored using foursquare API and the results were stored into a dataframe.


3.8. A list of top 20 venue categories in Boston Neighborhoods was created and plotted as a histogram.


3.9. A separated data frame was created only for the seafood restaurants along with their geographical coordinates.

 
3.10. K-Nearest Neighbors
For this project, K-Nearest Neighbors is the preferable algorithm for classification. K-Nearest Neighbors is an algorithm for unsupervised learning. Where the data is 'trained' with data points corresponding to their classification. Once a point is to be predicted, it takes into account the 'K' nearest points to it to determine its classification.
Elbow method to determine the optimum number of clusters
It's not always obvious from the scatter plot of the data what should be the optimum number of clusters. The most popular method for determining the optimum number of clusters for k nearest neighbour unsupervised algorithm is the elbow method; where the distortion is plotted against the number of clusters and the elbow in the plot represents the optimum number of clusters. From the plot below it is clear that the optimum number of clusters is 4.

![](https://github.com/SKandar-1/Figures/blob/main/Elbow_Method_K.PNG)

From the plot of distortion vs number of clusters, it is clear that three clusters will be optimum for k nearest neighbor modelling on this data set.
boston_seafood_grouped was merged with boston_data to add latitude/longitude for each neighborhood followed by sorting the data frame. 
Finally, a map of three clusters in the Boston neighborhood was created using the folium library.

![](https://github.com/SKandar-1/Figures/blob/main/Seafood_Restaurants_Cluster_Boston.PNG)



__4. Results__
Cluster 2, represented by purple circles in the map, has the highest concentration of seafood restaurants in Boston. Cluster 3, represented by green circles in the map has the second highest concentration, and Cluster 1, represented by red circles in the map has the lowest concentration of seafood restaurants in Boston.

__5. Conclusions__
Downtown Boston and the nearby areas have the highest concentration of seafood restaurants, marked by purple circles in the map. As a whole, the city of Boston and the surrounding neighborhoods have many indoor and outdoor activities and plenty of food choices; both American and international.This project provides a visual map with the highest concentration of seafood restaurants to help visitors who want to enjoy Boston's famous seafood.


__6. Acknowledgement__
This project is part of the IBM Data Science Capstone project in Coursera. Some codes for this project are reproduced from previous course materials. geeksforgeeks website (https://www.geeksforgeeks.org/) provided valuable resources for programming related concepts and clarifications.



