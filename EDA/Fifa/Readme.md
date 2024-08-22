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
