# March_Madness
*"This is March" - Jon Rothstein*

## March_Madness_EDA:
### Summary
This notebook is used to compare full team stats between various tournament teams from 2012-2021. The goal is to seek out particular stats that show a correlation to Tournament Performance.

### Data Source:
www.barttorvik.com for all raw data

### Initial Results:
Through the first iteration of EDA, the stats that showed correlation to Tournament Performance are listed below in order of importance:
- ADJOE
- ADJDE
- TOR
- FTRD
- 3P_D
- 2P_O

## March_Madness_Simulator:
### Summary
This is where the fun happens. Inside this notebook contains functions to predict the winners of 1 on 1 games as well as simulating each round of the tournament. The results from the simulation are stored in the sim_output folder, where you can find the winners of each round contained in a "roundofXX.csv" file.
### Results
I will keep track of each year's prediction model used in the game_prediction() function as well store the accuracy of the predictions after the tournament is completed. The results for each year can be found below:
### 2022:
- Predicted Champion: Gonzaga
- Predicted Final Four: Gonzaga, Kentucky, Houston, Kansas
- Actual Champion: Kansas
- Actual Final Four: Duke, UNC, Villanova, Kansas
- Percentile Finish (ESPN): 80.4 percentile
- Prediction % Correct (Outcome when all rounds were predicted Before First Round): 63%
- Prediction % Correct (Outcome when new predictions were made at beginning of Each Round): 73%
