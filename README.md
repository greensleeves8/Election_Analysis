# Election Analysis in Colorado

## Project Overview
A Colorado Board of Elections employee approached us to perform an audit of a recent local 
congressional election, assigning us to use Python to automate the process of answering the 
following tasks: 

1. Calculate the total number of votes cast.
2. Get a complete list of candidates who received votes.
3. Calculate the total number of votes each candidate received.
4. Calculate the percentage of votes each candidate won.
5. Determine the winner of the election based on popular vote.

## Resources
- Data Source: election_results.csv
-Software: Python 3.7.6, Visual Studio Code version 1.49.2

## Summary
The analysis of the election shows that:
- The total number of votes cast in the election was 369,711.

- The total number of votes by county in the precinct brokedown as such:
	- Jefferson County: 38,855 votes, for 10.5% of the total vote.
	- Denver County: 306,055 votes, for 82.8% of the total vote.
	- Arapahoe County: 24,801 votes, for 6.7% of the total vote.

- Denver County had the largest number of votes in the precinct, with 306,055 votes. 

- The candidates receiving votes were:
	- Charles Casper Stockham
	- Diana DeGette
	- Raymon Anthony Doane

- The candidate results were:
	- Charles Casper Stockham received 23.0% of the vote, with 85,213 total votes.
	- Diana DeGette received 73.8% of the vote, with 272,892 total votes.
	- Raymon Anthony Doane received 3.1% of the vote, with 11,606 total votes. 

- The winner of the election was:
	- Diana DeGette was the winner of the election, receiving 272,892 votes for 73.8% 
	of the total votes. 

![Election Results](https://github.com/greensleeves8/Election_Analysis/blob/master/analysis/Election_Results.png "Election Results")

## Challenge Summary
The code script used for this analysis should be able to be used with minimal adaptation for
other elections, provided that the source data is a similarly formatted .CSV file. The 
following code can be used as a template for importing a CSV file, as long as the folder and
file names are updated to reflect the correct file pathways, and creating lists and dictionaries
for candidates, counties, and vote totals, and creating strings and integers for output to 
determine the winning candidate:

![Import CSV](https://github.com/greensleeves8/Election_Analysis/blob/master/analysis/Code_Screenshot.png "Import CSV")

To open and read your CSV, use this code, updating variable names as needed:

```
with open(file_to_load) as election_data:
    reader = csv.reader(election_data)
```

To compile the names of the candidates and counties from a .CSV with a header row, and begin
vote counts for candidate and county (index numbers for columns may need to be changed to the
appropriate number if the election data has additional information columns):

```
header = next(reader)

for row in reader:

    total_votes = total_votes + 1

        candidate_name = row[2]

        county_name = row[1]

        if candidate_name not in candidate_options:

            candidate_options.append(candidate_name)

            candidate_votes[candidate_name] = 0

        candidate_votes[candidate_name] += 1

       	if county_name not in counties: 
        
            counties.append(county_name)

            votes_by_county[county_name] = 0

        votes_by_county[county_name] += 1
```



Election-Audit Summary: In a summary statement, provide a business proposal to the election 
commission on how this script can be used—with some modifications—for any election. Give at 
least two examples of how this script can be modified to be used for other elections.
