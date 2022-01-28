# Predicting Workload for Pitchers
## Design
The scope of this project is to create a regression model that predicts a pitcher's innings pitched (IP) for a season based on quantitative data from the previous year. The requirement for a team to be responsible for 1458 innings over the course of a season was particularly relevant during the 2021 season, when several injury records were shattered, leading to fewer innings pitched per player. Often, in baseball statistics, rate stats such as ERA are favored when comparing pitchers instead of bulk stats like IP. This project aims to make a prediction on statistic that may be overlooked in the industry.

The results of this project can be interpreted to help team owners more strategically budget their payroll to ensure that they can account for the volume of the season, as focusing on rate stats alone could cause there to be a shortage of production from salaried players.
## Data
Data for this project is taken from baseballsavant.mlb.com. Baseball Savant has a database of classic stats (home runs, batting average, strikeout %) along with advanced Statcast metrics (fastball velocity, sprint speed, launch angle, pitch movement) only available from 2016 onward. Part of the scope of this project is to combine the Statcast metrics with classic metrics to see if a better model can be made than with just classic metrics alone. Selenium was used to operate dynamic web pages, while BeautifulSoup was used to parse the html and scrape the data.
After scraping, 1314 data points were acquired. The target was the next year's IP, and the features used were player Age, Games, Innings Pitched (IP), Strikeout Percent (K%), Walk Percent (BB%), Slugging (SLG), On Base Percent (OBP), Earned Run Average (ERA), Exit Velocity (EV), Launch Angle (LA), Sweet Spot Percent (SWEET%), In-Zone Percent (ZONE%), Whiff Percent, Swing Percent, Fastball Velocity (FB_SPEED), Fastball Break (FB_BREAK), Breaking Ball Percent (BREAKING%), and Average Breaking Ball Break (BREAKING_BREAK).
## Techniques
- Feature Engineering
-- Pitchers were determined as either starters or relievers based on a function of IP and games played
-- Polynomial features were attempted, but a linear model prevailed
- Linear Regression and LASSO Regression was compared for the model, with the Linear Regression proving to be more effective
-- Both models were cross-validated with a KFold of 7
-- Residual plots were made to identify possible weaknesses in the model
- A LASSO Regression plot was made to visualize which features stay relevant as lambda increases.
## Tools
- BeautifulSoup and Selenium were used for web scraping
- sklearn was used for linear regression, lasso regression, standard scaling, and cross validation
- pandas and numpy were used for general database manipulation
- matplotlib and Seaborn were used for data visualization
## Communication
The model's R-squared value was 0.45, so the biggest takeaway is perhaps that this is an area in which there can be a tremendous amount of variance. It's not uncommon for a pitcher to have a normal statistical season, then be injured or ineffective the next season and throw very few innings. Far and away the most telling features for predicting future innings pitched were the IP total of the previous season and whether the pitcher was a starting pitcher or not. Strikeout % and Walk % were also predicting factors. While traditional metrics were most informing, I was pleased to see Fastball Velocity, a Statcast-only metric, as one of the top features.
Future goals would be to try some different techniques with the same data to try to limit the variance and heteroskedasticity. I would also try to add features not available on Baseball Savant, like injury history. Finally, I might try to predict other targets, such as ERA+ or WAR.
