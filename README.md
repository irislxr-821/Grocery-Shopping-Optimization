# Grocery-Shopping-Optimization
Tools: Python (Gurobi Package)
## Description
As a student, I faced challenges in finding affordable, quick, and nutritious food options. This spurred me to launch a project aimed at developing a model that offers users personalized, low-cost grocery lists. This model considers individual nutritional needs and travel time, catering to others facing similar issues.

## Objective
The model aimed to minimize grocery and travel costs while adhering to constraints on transportation, nutrition, diversity, and allergies. It was designed to recommend the most cost-effective store and mode of transportation for grocery shopping, with the option for users to pre-select their travel method. Initially, it assumed the user lived on the University of Toronto campus, focusing on selections from seven specific stores and various transportation options, including driving, walking, biking, and public transport. To illustrate its adaptability, the model also accounted for specific dietary restrictions, such as a peanut allergy.

<p align="center">
<img src="./images/Location-Map.png" width="50%" > 
</p>

<p align="center">
Locations of grocery stores with respect to the origin
</p>

## Data Collection
The optimization model's data came from the University of Toronto's Food Labelling Information Program (FLIP), managed by L'Abbe Lab. The FLIP database, updated every 3-4 years, includes details on packaged foods across Toronto stores. Our model used the 2020 dataset, notable for linking items to specific retailers and listing prices, alongside information on food categories, packaging, serving sizes, and nutritional content. Distance and travel time data were sourced from the Google Maps API, focusing on the shortest routes and corresponding times between the user's starting point and the seven selected stores, aligning with the model's premise of choosing a single store for shopping.


## Methodology
The objective function was composed of two parts. The first part was the cost of purchasing grocery items, which was calculated by the quantity of chosen items multiply the prices. The second part was the cost of traveling.
<p align="center">
<img src="./images/Objective Fuction.png" width="50%" > 
</p>
There are 6 different types of constraints:
<br>
•	Frequency Constraint - Users only want to visit one store at a time <br>
•	Travel Constraint - Control the amount of time a user is willing to spend on travel <br>
•	Nutritional Constraint - Desired weekly nutritional intake <br>
•	Diversity Constraint - To ensure variability of products in the input <br>
•	Quantitiy Constraint - Control the quantitiy of each item in the output <br>
•	Allergy Constraint - To exclude certain ingredients in the output <br>


## Results
The output of the linear optimization model determined Joe’s No Frills as the optimal grocery to shop at along with biking as the optimal mode of transportation. These results satisfy the travelling time constraint as well as minimize the travelling cost. The total cost of all the items at Joe’s No Frills is $28.36. 

## Conclusion
The purpose of this project is to provide people with an accessible way to obtain cheaper food while satisfying nutritional requirements. Therefore, to make the whole process more convenient, we recommend developing a mobile application that focuses on customizing the grocery shopping list for an individual user at the lowest cost. Building upon the basis of our model, the application should include three major functionalities. 
<br>
•	Customization: Allow users to input their personal information, such as age, weight, height, and workout habits. The application will automatically calculate the best nutritional intake suggestion to ensure a healthy diet. <br>
•	Dietary Preferences: The algorithm will also seek to meet all the preferences that a particular user has. For instance, referring to the previous section, more claims, such as vegan and gluten-free. Users can also incorporate specific recipes into their diets. <br>
•	Traveling Preferences: To ensure users can easily access the recommended locations, they are encouraged to specify their preferred traveling method, traveling time, as well as the maximum number of stores they are willing to visit.  <br>

## Files
Refer to Optimization-Report.pdf for detailed procedural explanations. <br>
[Optimization-Report.pdf](Grocery-Shopping-Optimization/Optimization-Report.pdf)
Refer to Optimization-Code.ipynb for the Python code.
