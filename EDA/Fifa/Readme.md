## EDA on Fifa World cup data

- I have used 3 different data files containing following information:

  1. Fifa ranking - world ranking of each team in football
  2. Matches - Information about all the world cup match teams, penulty, substituion, red/yellow card info
  3. Worldcups - Since the 1st edition till the last edition of worldcup; winner, top scorer, runner-up, match attendance

# I have focused in calculating the inference of the data and not focusing on the ML point of view.

- The data is ranging from 1930 to 2022.

- Point to be noted: After 2nd world war 1949, Germany DR and West Germany were the 2 parts of 'Germany'. After 1910, these parts were combined again. So, the team data column needs to be changed.

## Starting with basic EDA

_1st Inference_

- Calculating stats of the data

- plotting pie chats of winner, 1st runners up and 2nd runners up

- Calculating Winner is easy from the world cup table and Champion column and 1st Runners up from Runners_up column

- From the matches table, 1st and 2nd runners up, need to check which team won the match by scoring more goals, and if tie, who won in the penulty shoot-out.

- Instead of using Matplotlib, I have used plotly liberary, to draw subplots and also it gives information on hover and can customized the display information in the way we want

# Always write conclusions at the end of each information gain because it helps us to summerize the information we have obstracted from the data till point.

_2nd Inference_

- Which team participated in which year to play FIFA, which can get by grouping by Year column and getting the information of Home team and Away team

- There will be duplicates in the data because a team could have played multiple matches through out the year. So, aggregating the list of home team and away team in Set and then converted into List.

- explode(): Simplyfy the handling of nested tuples, dictonaries, lists by converting a list-like structure into a saperate rows

- Finding which team has played in which edition of FIFA, can be determind using 'Heatmap'. nd Oberservations in the end.

_3rd Inference_

- From the world ranking table, analyzing using the current rank and pervious rank, which team's rank Increased, Decreased or unchanged

- Making 3 list of different categories is not a best way to present the data. So, I opt to make a dataframe of these data and 1st step is to equalling the length of the data.

# ADVANCED EDA

- Observe the data

_1st Inference_

- Probability of a team winning the knowckout matches

- Suppose, for team Argentina, taking the information of total matches played in Knockout matches(Final, Semi-Final, Quarter-Final).

- Grouping the data by round, So I can have the total count of respective matches. Then, calculating the no of matches, where Argentina won those matches.

- Combining these 2 dataframes and finding the probability of winning the mathces.

- A general function to calculate the performance of any team in such matches.

_2nd Inference_

- Checking the Playing Strategy of a team in knockouts vs non-knockout matches

- home_goal column contains the information of a goal: it's time and player who made the goal

- The data has specific format in the column, there is a pattern in the data, so it will be easier to extract the numbers from the data

- Creating 4 different dataframes, home team & away team in knockouts and non-knockouts.

- 're()': a RegX module. A built in liberary of a python that provides regular expression support.

- Firstly, I need to have the pattern of the string, So copy the string and ask GPT to give the regX pattern.

- For Knockouts; Adding two columns, Home_goals and Away_goals; representing the time of a goal by perticular team

- A perticular team can be home team and away team as well. So, to find the strategy we need to saperate out these two columns and aggregate for a perticular team

- Making a dataframe of Home_goals and Away_goals, filling empty and null values with 0. Then, excluding those rows where goal count is 0.

- Adding another column, Time of Goal by calculating whether the time is <45, 45 < time < 90 or >90. and getting the strategy of knockouts. Same goes for Non-Knockouts.

_3rd Inference_

- Does the Substitution turns out fruitful for a team or not

- 2 ways to make this decision fruitful: Either substitute player score a goal or team score improved after subsitution

- There can be multiple substitution in a single match from a perticular team. So, after each substitution time, the above two conditions need to be checked.
