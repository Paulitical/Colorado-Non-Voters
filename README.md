# Capstone: Registered Non-Voters and Predicting the Election if everyone voted

In this repo, I will be going through my Capstone Project I did for the General Assembly Immersive program. This project was about Colorado Registered Non-voters in the 2016 presidential election and how the elections results would change if every registered voter voted. I also looked at an election survey of likely voters and if I can model how I think the population as a whole would vote.

## Data

Most of the data came from the [Colorado Secretary of State's website](https://www.sos.state.co.us/). I exported the files for registration and voter data in Excel because it needed to be Delineated and was not converting well so I had to do some editing that was easy to do in Excel. 
I also gather data from (http://coloradovoters.info/) and (https://electionstudies.org/).

## Analysis

With the registrations, ballots and votes data I did some calculations to get some more information out of the data. I wanted to find the number of registered non-voters numbers by party. I used the registration numbers of each party and subtracted the number of ballots cast by each party to get to the registered non-voted by each party. 
I also wanted to determine how each party ended up voting, so I made some assumptions:
  1. If Dems or Reps got fewer votes than ballots cast, I assumed they voted for the opposite party
  2. If Dems or Reps gained votes I assumed they came from Independent votes
  3. I assumed all Dems and Reps voted for their own party
 From here I used Native Bayes to calculated posterior distributions for how I would predict Non-Registered to vote. This was not a very predictive model and could get an accuracy score to see how well my model was performing so I decided to try a similar but different data set to be able to see how well I was predicting.
 
 The next model I created was using ANES survey data, asking people who they planned to vote for in the 2016 presidential election. This dataset also had age and party affiliation which I used as my predictive variables (X) and how they said they would vote as my target (y).
 I tried several different models to see which had the best accuracy and best ROC AUC score.
 
 
 ## Results
 
 Applying Native Bayes to the non-registered votes did increase Democrats and Republicans votes, and decrease Independents. Democrats gain more votes than Republicans increasing there lead over Republicans.
 
 When I used the ANES, Support Vector Classifier returned the most accurate scores which seems logical because it is using the maximum-margin hyperplane which is useful when determining between two obvious feature like Dem vs Rep, but it would also make sense that could would do a good job at find separation of age and gender for Independent voters.

