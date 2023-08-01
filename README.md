# Final-Project-Statistical-Modelling-with-Python

## Project/Goals

The goals of this project is to showcase and reinforce my learnings in the areas of:

1. Accessing data from website using APIs. 

2. Cleaning and transforming data retrieved via API using Python.

3. Loading data into a database using Python.

4. Performing EDA, including using both statistics and visualizations.

5. Identifying trends and patterns in data using statistical models.

6. Interpreting the results of the statistical models.


## Process

Step 1. Data Gathering

a) Data retrieval from CityBikes (https://citybik.es/) 

- I used CityBikes API + Foursquare API_KEY to retrieve information about bikes for the city Slough in England.

- normalized retrieved data (json format) layer by layer until the contents of station displaying as dictionary are extracted into columns.

- created a new dataframe containing name, free_bikes, empty_slots, total_slots, normal_bikes, online, longitude and latitude for the city Slough.
 

b) Data retrieval from Foursquare (https://developer.foursquare.com/places)

- I chose two points of interests (POI): (i)Bakery (ii) Employment Agencies

- put in a request to get information about my choice POI in Slough

- For efficiency, I ran a code to pull Bakery and Employment Agencies information the same bike locations from City Bikes response. To achieve this, I exported my dataframe from Part 1 (City Bikes notebook) into Foursquare and Yelp notebook. The code looped through the latitude and longitude information in the dataframe.



c) Data retrieval from Yelp (https://www.yelp.com/developers/documentation/v3/get_started)

- Yelp required a different API Key so needed to create apps on Yelp website to get the API key


Step 2. DataFrame merge

- I used the concatenate function in Python to merge all dataframes into a single one.

df_merged = pd.concat([df_1,df2, df3...dfn], ignore_index=True, sort = False)

Step 3.

Performed exploratory data analysis (EDA) to have a general feel of ehat the data looks like and using statistical analysis and visualizations.

Step 4. Saved the combined dataframe to SQLite

Step 5. Built statistical model using OLS method with Free_Bike as the dependent variable.



## Results
(fill in what you found about the comparative quality of API coverage in your chosen area and the results of your model.)

- Generally speaking, the API coverage does not sufficiently cover parameters that have high explanatory power in predicting the dependent variable. More information captured in Notebooks. Not all conditions for Linear regression was satisfied.

- Dataset is mostly normally distributed.

- Linearity between Dependent & Independent variables is not distinct.

- There exists some collinearity between some of the Independent variables.

- Need to include variables that will satisfy Linear model assumptions and improve the model performance. 


## Challenges 
Time was a major constraint

Automating the process of retrieving data from Yelp was a pain. I needed to increase my search radius in Yelp in order to reduce time and effort to manually send request because of the failed code.



## Future Goals
- I would increase my search radius so get more bike stations and increase my data for restaurants and employment agencies.

- Find out the definition of the parameters (data columns) for better understanding of the dataset. 

- Investigate that the dataset is consistent with all assumptions for a Linear Regression Model.

- Review failed code or figure out another way to automate sending request to Yelp for many locations.

