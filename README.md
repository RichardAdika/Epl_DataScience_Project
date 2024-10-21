# Premier League Players Stats Analysis ⚽️  

---

## Project Overview  
I started this project by importing the necessary libraries:  
- `pandas`  
- `matplotlib`  
- `numpy`  
- `seaborn`  

I worked with two dataframes, `df_1` and `df_2`, both containing Premier League players' stats but with different columns. I inspected both datasets and noticed that the columns in `df_2` were in rows, and the rows were in columns. To fix this, I transposed `df_2` and reset its index, renaming the index to `'Players'`.

Next, I renamed the columns in `df_1` to make them more understandable:
- `PLAYER` -> `Player`
- `TEAM` -> `Team`
- `GP` -> `Games_Played`
- `GS` -> `Games_Started`
- `MIN` -> `Minutes_Played`
- `SHOTS` -> `Shots`
- `GOALS` -> `Goals_Scored`
- `ASST` -> `Assist`
- `SOG` -> `Shots_On_Goal`

Afterward, I reinspected the datasets and checked for null values before proceeding.

---

## Analytical Questions  
I aimed to answer 14 questions based on:
1. Descriptive statistics
2. Correlation and regression
3. Team performance
4. Descriptive analysis

---

## Question 1: Which team has the most players with 10+ goals scored?
- **Method**: I used `groupby`, `count`, and `sort_values` functions on `df_1` to determine that Manchester City had the most players with 10+ goals.

---

## Question 2: Who are these players?
- **Method**: By subsetting `df_1`, I identified the Manchester City players with 10+ goals.

---

## Question 3: What is the average minutes played per game for players who score 5+ goals per season?
- **Method**: Using filtering and the `mean` function, I calculated the average minutes played per game.

---

## Question 4: Which position has the highest average shots on goal per game?
- **Method**: I merged player positions from `df_2` into `df_1` and named the new dataset `new_epl_data`. After dropping null values, I grouped the data by position and calculated the average shots on goal.

---

## Question 5: What is the distribution of games started among players?
- **Method**: After normalizing the data, I created a bar chart to visualize the distribution.

---

## Correlation and Regression Analysis (Questions 6-10)

---

### Question 6: Is there a significant correlation between minutes played and goals scored?
- **Method**: I used Seaborn's `regplot` and calculated Pearson's correlation coefficient. The result was 0.40 with a p-value of 0.00, indicating a moderate positive correlation.

---

### Question 7: How does the number of shots on goal relate to assists?
- **Method**: I computed Pearson's correlation (0.543), showing a moderate positive relationship. I also ran a linear regression analysis, which confirmed the positive correlation.

---

### Question 8: Can we predict goals based on minutes played and shots on goal?
- **Method**: I built a linear regression model. The key metrics were:
  - **MSE**: 1.51
  - **R² score**: 0.79
  - **Intercept**: -0.2795
  - **Coefficient for minutes played**: -0.00039
  - **Coefficient for shots on goal**: 0.2146

---

### Question 9: Does the number of games started impact player performance?
- **Method**: I used `regplot` and observed a weak correlation between games started and goals scored, though assists increased with more games played.

---

## Team Performance Analysis (Questions 10-12)

---

### Question 10: Which team has the highest average goals per game?
- **Method**: Using the `groupby` function, I found that Leicester City had the highest average goals per game.

---

### Question 11: Do teams with more players scoring 5+ goals perform better in the league?
- **Method**: In the 2015/2016 season, Manchester City was the only top-4 team with more than two players scoring 5+ goals.

---

### Question 12: Is there a relationship between team success and player performance metrics?
- **Method**: Based on goals and assists, top players from Leicester City, Arsenal, and Manchester City contributed significantly to their teams' success.

---

## Descriptive Analysis (Questions 13-14)

---

### Question 13: Compare the performance of top scorers.
- **Insight**: Among the top 10 goal scorers, only one midfielder was included.

---

### Question 14: How do midfielders from different teams compare in terms of assists and shots on goal?
- **Method**: A bar chart showed that Southampton had the most midfielder goal scorers, while Norwich had the most midfielders contributing assists.

---

## Conclusion  
The analysis showed that no single factor contributes to a team's or player's performance. Various metrics combine to influence the outcomes, and further exploration of additional variables could provide deeper insights.
