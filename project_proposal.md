# Metis Project 2: Regression
## Background
Major League Baseball (MLB) is a $66 billion industry, and is considered the premiere baseball league around the world. In order to complete a season, teams must account for roughly 4500 outs over 1500 innings. Pitchers are the players most responsible for recording these outs, and thus command a high salary. However, when a team signs a pitcher to a big contract there is no guarantee that the player will be able to live up to their workload responsibility due to injury or loss of effectiveness. This project will look at trends from a pitcher's previous performance to see what factors predict future performance.
## Data Description
Sites used:
* baseball-reference.com
* baseballsavant.mlb.com
Data Target:
* Innings pitched (IP)
Data Features:
* ERA+
* IP of previous season
* IP of career
* Fastball velocity
* Change in fastball velocity
* Age
* Walk rate
* Strikeout rate

A player's previous performance and career history will be used to try to inform their next season's innings. This will include their previous season's statistics, their cumulative totals, and also a comparison of their recent performance to their own precedence.

Baseball-reference can be used for all of the basic statistics. I hope to use baseballsavant for its advanced metrics and measurements, such as fastball velocity, spin rate, and movement, though data for that only goes back to 2015.
## Tools
* Beautiful Soup will be used to scrape statistics from the reference website
* Selenium may be necessary depending on needs from the baseballsavant website
* Seaborn and scikit-learn will be used to help visualize the data and develop the model 
## MVP Goal
A minimum viable product will model IP of a season based on past performance, while future iterations of the project will hopefully include advanced metrics.
