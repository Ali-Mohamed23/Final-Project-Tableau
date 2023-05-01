# Final-Project-Tableau

## Project/Goals
My goal for this project is to utilize the skills learned in Tableau this week to turn data into easily consumable visual insights. Create impactful dashboards that help make decisions based on business questions. Lastly, communicate insights with the correct visualizations. For this project I will be using the 2018 FIFA player ratings dataset.

## Process
### Step 1: Connect the data.
My first step was to download the FIFA 2018 player ratings dataset and get an understanding of the data. After downloading the dataset I uploaded it into Tableau as a csv connection. In this dataset there was an important data type that was missing which is time-series data. While I was looking at all the different fields I found that there was no date field and understood that all of the data should be interpreted as player ratings for one point in time. The table had 70 different features which were mainly player positions, and attributes. So I had to understand what information I could get from this data. 

### Step 2: Build different Visualizations
There were roughly 18000 rows of different players with many different ratings. So I started by bulding different visualizations to get an understanding of the data. I could put the wage in a column and age of players to get the distribution of the wages in relation to the age of the players. After building different visualizations I learned that much of the data was scaled between player ratings for different attributes that a player possesses on a scale of 0-100. There are many different positions in soccer as well. 

### Step 3: Identify the important features in the dataset.
The important features in the dataset that I identified that I could use to gain valuable insights are:
- Overall player rating (This is a combination of all the players attributes to into one rating)
- Country
- Clubs 
- Player ID ( This was important because it is unique for each player)
- Player Names
- Positions: 
- Attributes: Ovr, acceleration, ball control, finishing, strength, shot power, sprint speed.
- Wage 
- Value 

With these features in the data set I could answer many questions. 

### Step 4: Create visualizations with Maps, Analytical visuals, Show Me Tables, Clustering and Forecasting.

Maps - I put the nationality as a column input and then used the show me table to turn it into a map. I then added the unique player ID as a count in the detail mark. This now gave me the a map with the count of each player per country. Furthermore, to get more detail on the map I created a parameter with a list of attributes I viewed as important from step 3. I then used a calculation field that computes the average of each attribute:
```SQL
Case [Attribute]
When "Overall" THEN AVG([Overall])
```
I then created an attribute label calculated field so that I can see which attribute I am looking at in the details. Lastly, I show parameter on the parameter I created and put average attribute as a colour mark, and attribute label as a label mark. 

I can now view the count of players in a country and filter through the average attribute level of my choice. This visualization can answer many questions from which countries have the fastest average players or overall of players.

Questions: Which countries have the highest average attributes and player counts?

Result: Ghana has the highest average acceleration from countries with over 100 players in the dataset.

Challenge: The average includes all players in each country, therefore a country with many goalkeepers may change the average for the attributes of all players. 

Analytical Visuals - I used the clubs as a column input and overall as a row input. I then filtered the clubs to show the top 10 the highest average overall and converted to an box and whiskers plot that shows the name in the details mark. I created another box and whiskers plot for comparison of the clubs and wages. I created another chart with the countries with the most amount of players and sorted them by highest overall average. The result was that Brazil had the highest overall average amoungst the countries with the most players. I chose the most amount of players because it would not make sense to compare countries with very few players to the averages of countries with many players. 

Question: What are the clubs with the highest overall averages? Is there a relation with the wage that these clubs are paying?

Result: There was a relation to how much the clubs with the highest average overall rated players, with the amount the clubs were paying in wages. FC Barcelona and Real madrid Had the highest wages paid and highest overall rated players average. Brazil had the higest overall average amoungst the countries with the most players. 

Heatmap - I created a heatmap that takes the postition of players, and gets the average of the attributes for those positions. I did this by putting preferred postion as a column input and measure names as a rows input. I then filtered the measure names for the attributes I wanted to get an average for. Lastly, I put the measure values as marks for color and label.

Question: What attributes does each position require?

Answer: A striker needs a lot of strength as that is the highest average for the striker position. 

Analytical bar chart Top players by position - I used a parameter called position and added all the position into it. I then created a calculated field that averages each position value. I used this calculated field as a column input and the player name as a row input. I then show the parameter position, and filtered the data to show top 10 highest measures for that position.

Question: What are the top players for each position?

Results: Cristiano Ronaldo and Lionel Messi were the top rated strikers.

Cluster - I created a cluster of players based on their wage, overall rating, and value. This could be beneficial if someone is looking for a player within a certain price-range group. You could isolate that cluster group and view players and their overall ratings. 

### Step 5: Create a dashboard & stories

I added some of the visualizations to a dashboard and created stories for each of the visaulizations to explain the insights from each visualization.

## Challenges 
There were many challenges during this project for instance I wanted to create a forecast, however it was difficult to create since there was no time series data. All of the data was for one point in time so I could not figure out how to create a forecast from this data. 

## Future Goals
If I had more time I would try to use age as a forecast for what wage a player would get paid. I could not figure out how to use age as a forecast for wage in this data. 
