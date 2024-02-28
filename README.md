# Grocery-Shopping-Optimization
Tools: Python (Gurobi Package)
## Description
As a student at that time, I was struggle with how to find food in the cheapest and fastest way while maintaining the neccessary nutritions. This idea inspired me to start a optimization project deliver not just for me, but people with the same concerns a model that provides the lowest-cost grocery list per user by considering lifestyle factors such as desired nutritional intake and travel time.

## Objective
The basic model was built by minimizing the cost of purchasing grocery items and the cost of traveling to the grocery store, subject to transportation, nutrients, diversity, and allergy constraints. The objective of the model was that it would automatically determine one store the user should visit for groceries, as well as one recommended traveling mode to achieve the lowest cost. The later part, however, can also be pre-selected by the user. For our model, the user was assumed to reside on the campus of the University of Toronto, and thus, the origin of travel. The stores to be chosen are two Loblaws branches, two No Frills branches, one Metro branch, one Walmart branch, and one Grocery Gateway branch. The modes of transportation include driving, walking, biking, and public transport. The user is assumed to have an allergy to peanuts to demonstrate the model’s capability of excluding a particular type of ingredient.

<p align="center">
<img src="./images/Location-Map.png" width="50%" > 
</p>

<p align="center">
Locations of grocery stores with respect to the origin
</p>

## Data Collection
The data on which the optimization model was built was obtained from the University of Toronto’s (UofT) Food Labelling Information Program (FLIP) curated by the L’Abbe Lab. Data in the FLIP database contains information about packaged food items across different stores in Toronto that is updated every 3-4 years. The application of our model was restricted to the data in the 2020 dataset, as it was the first dataset to map items to the retail stores and include item prices. The data also includes information about item characteristics, such as their food category, container weight, serving size, and nutritional value per serving.  
The distance and time information were obtained by retrieving a distance matrix from the Google Maps API. Since our model assumes that the user will want to visit only one store when grocery shopping, only the distances of the shortest paths between the origin and all the seven stores and their corresponding travel times were kept. 



## Methodology
The objective function was composed of two parts. The first part was the cost of purchasing grocery items, which was calculated by the quantity of chosen items multiply the prices. The second part was the cost of traveling.
<p align="center">
<img src="./images/Objective Fuction.png" width="50%" > 
</p>
There are 6 different types of contraints:
<br>
•	Frequency Constraint - Users only want to visit one store at a time <br>
•	Travel Constraint - Control the amount of time a user is willing to spend on travel <br>
•	Nutritional Constraint - Desired weekly nutritional intake <br>
•	Diversity Constraint - To ensure variability of products in the input <br>
•	Quantitiy Constraint - Control the quantitiy of each item in the output <br>
•	Allergy Constraint - To exclude certain ingredients in the output <br>


## Results


## Conclusion
