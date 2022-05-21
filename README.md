# Election Analysis

## Overview of Election Audit


## Election-Audit Results
### Total Votes in the Election
<!-- How many votes were cast in this congressional election? -->
There were 369,711 votes cast in the congressional election. This value was determined by having a 'for' loop run through each row in the 'election_results.csv' file and tally each ballot that was cast. A picture of the code used can be found below.

#### Total Votes Code
![ian-zukowski](Total_Votes_Code.png)
<!-- (44-48) -->

### Election Data by County
<!-- Provide a breakdown of the number of votes and the percentage of total votes for each county in the precinct. -->
<!-- Which county had the largest number of votes? -->
The three counties which participated in the election were Denver, Jefferson, and Arapahoe counties. The county with the most voters was Denver county. It comprised 82.8% of the vote with 306,055 ballots cast. The second largest county was Jefferson county, which supplied 10.5% of the votes with its 38,855 ballots. The smallest county was Arapahoe, which comprised 6.7% of the votes with 24,801 ballots cast.
These values were obtained from the 'election_results.csv' file by creating a conditional statement which selected the name of the county on each ballot and appended the county into a list if it was not already present. 
In a separate dictionary (consisting of Key:Value pairings made from County Name:County Votes) the County Votes values were then set to equal 0. And as the code cycled through each row, that value was increased by 1 if the County Name was matched in column 2 of that row.
A picture detailing the code used to find each county's vote count can be found below.

#### County Votes Code
![ian-zukowski](County_Votes_Code.png)
<!-- (69-80) -->

After obtaining the vote count for each county it was further necessary to obtain that result as a percentage of the total votes in the election. To find this percentage, each entry in the County Votes dictionary was referenced in a new 'for' loop to obtain the total votes for a county. That value was then divided by the total votes (369,711) and reformatted as a percentage.
To find the county with the most votes, the same 'for' loop was utilized. For this calculation an empty integer and string variable were made to hold values for the vote count of the largest county, and the name of the largest county. As the 'for' loop ran through the dictionary, it checked if the current county had a vote count larger than the previous counties. If the vote count was the highest in the list so far, then the empty variables stored the value and key from that entry of the dictionary. This code returned the known value that Denver county had the largest voter turnout with its 306,055 ballots.
The described code can be found in the picture below.

#### Largest County Code
![ian-zukowski](Largest_County_Code.png)
<!-- (96-115) -->

### Election Data by Candidate
<!-- Provide a breakdown of the number of votes and the percentage of the total votes each candidate received. -->
The candidates in the election were Diana DeGette, Charles Casper Stockham, and Raymon Anthony Doane. The candidate with the highest vote total was Diana DeGette who recieved 73.8% of the votes. This value represents the 272,892 ballots which were cast for Rep. DeGette. The first runner-up was Charles Casper Stockham. The 23.0% of the votes that Mr. Stockham earned represents 85,213 ballots. Finally the candidate with the least votes was Raymon Anthony Doane. Mr. Doane recieved 3.1% of the votes, which represents 11,606 ballots.
The code to find these values followed a similar pathway to the code used to breakdown the results by county above. In the 'election_results.csv' file a conditional statement was created to select the names of unique candidates and add them into a list if the name was not already present.
Then in a separate dictionary (consisting of Candidate Name:Candidate Votes for the Key:Value pairings) the Candidate Votes were set equal to 0. And as the code cycled through each row, that value was increased by 1 if the Candidate Name was found in column 3 of that row.
A picture detailing the code used can be found below.

#### Candidate Votes Code
![ian-zukowski](Candidate_Votes_Code)
<!-- (56-67) -->

<!-- Which candidate won the election, what was their vote count, and what was their percentage of the total votes?  -->

After obtaining the vote count for each candidate it was further necessary to obtain that result as a percentage of the total votes in the election. To find this percentage, each entry in the Candidate Votes dictionary was referenced in a new 'for' loop to obtain the total votes for a county. That value was then divided by the total votes (369,711) and reformatted as a percentage.
To find the candidate with the most votes, the same 'for' loop was utilized. For this calculation an empty integer and string variable were made to hold values for the vote count of the leading candidate, and the name of the largest candidate. As the 'for' loop ran through the dictionary, it checked if the current candidate had a vote count larger than the previous candidates. If the vote count was the highest in the list so far, then the empty variables stored the value and key from that entry of the dictionary. This code returned the known value that Rep. Diana DeGette won the election with 272,892 (73.8%) of the votes.
The described code can be found in the picture below.

#### Winning Candidate Code
![ian-zukowski](Winning_Candidate_Code)
<!-- (132-151) -->

## Election-Audit Summary
Will gather the same information for any election because:
(1) guaranteed to gather all candidates
(2) guaranteed to gather all counties
(3) will output percentage votes and determine in all events but a tie


In larger elections the code would need to be modified to account for the following additional factors:
(1) Ballot Measures and other election results
(2) Election data coming from separate counties/districts

To address the first point, it is important to keep in mind that most general elections have additional ballot measures including elections for other local government officials and ballot initiatives and referendums. To count these results the code could be modified in the following way:
    (1a) Create an empty list and dictionary before the initial 'for' loop
    (1b) Create an empty 'winning_result' string and 'winning_percentage' variable equal to 0.
    (2) In the 'for' loop, append the relevant unique vote results (i.e. Candidate Names or Yes/No) into the empty list
    (3) Link the dictionary to this list, with the vote results as the Key. Add 1 to the value associated with that key.
    (4) Create a new 'for' loop that runs through the entries in the dictionary.
    (5) Set a variable to find the value associated with each key in the dictionary.
    (6) Divide that value (as a float) with the total votes in the election to obtain a 'value percentage'.
    (7) Check whether the 'value percentage' is larger than the current 'winning_percentage'. If so, then set this value as the new winning percentage, and its associated key as the 'winning_result'.

Another point that may need to be addressed is the larger turnout and voting system associated with statewide and national elections. In these larger elections, the single file used here (representing Colorado's 1st District) would need to be used in conjuction with the results from the six other congressional districts. To count all of these results in the same code the following modifications could be made:
    (1) Have a distinct name to reference each file which will need to be read (i.e. instead of "file_to_load", reference "file_to_load_1")
    (2) Run the same code for "file_to_load_1"
    (3) 



Suggestion 1: Breakdown candidate vote per county
Suggestion 2: Account for ballot measures/other issues that are being voted on
Suggestion 3: Breakdown votes per demographics (assuming gathered in separate database)
Suggestion 4: Change code to account for a tie?
Suggestion 5: Account for sample error/recount margins?
