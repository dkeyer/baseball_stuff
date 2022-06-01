# Beat The Streak Analysis

## Table of Contents
1. [Objective](#Objective)
2. [Background](#Background)
3. [Data Choices, Extraction, Cleaning, and Analysis](#Data_Choices)
4. [Use Case Scenario](#Use_Case_Scenario)

### 1 - Objective <a name="Objective"></a>
Beat the Streak is a fantasy game created by MLB.com. The goal of the game is to pick an MLB player (or 2 players) to get a hit each day. If your selected player hits, you extend your streak. If the player does not hit, your streak ends. The player with the longest streak at the end of each season is declared the winner, and a streak of 57 wins you the grand prize of $5.6 million.

The goal of this project is to select the most likely MLB players to get a hit each day. In other words, the best candidates to pick for Beat the Streak

### 2 - Background <a name="Background"></a>
My strategy in Beat the Streak involves not only choosing a player who is hitting well, but also exploring other variables. The other most important thing to me is the opposing pitcher's prior performance, but I also consider some other things which I will detail in the next section.

### 3 -  Data Choices, Extraction, Cleaning, and Analysis<a name="Data_Choices"></a>
The first thing I needed to do was get my data, which I (primarily) got from Baseball Savant. I also use two other small datasets from Rotowire because it (as of writing this) isn't possible to get a CSV from Baseball Savant which includes a player's team. So I got the CSV from Rotowire with the players' team names and merged them together.

I scrape all of the probable pitcher data using Beautiful Soup from MLB.com, sometimes at the time of running the notebook, not every pitcher will be announced, but the notebook is setup to assign 'TBD' as the starting pitcher for whichever team(s) have not yet announced their starter.

The model is based mainly on expected batting average (xBA). Many traditional models and prediction techniques use regular Batting Average, but I believe xBA (with the help of Statcast which collects all kinds of data in MLB ballparks like exit velocity, launch angle) is a better indicator of future performance. Other features that I consider are strikeout %, walk %, and handedness.


### 4 - Use Case Scenario <a name="Use_Case_Scenario"></a>
This analysis can be used to help optimize picks for any player who plays beat the streak. The notebook is setup to run daily without the need to change anything, so it will generalize well for the future and I can focus on improving the accuracy and engineering more advanced features.
