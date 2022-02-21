# Assessing Trae Young's impact on his teammates

Two-time NBA All-Star Trae Young has the highest player efficency rating on the the Hawks. But I wanted to know, how *more* efficient does he make his teammates when they play together? Using NBA.com's two-player line-ups, I compare Young's performance with his teammates against his teammates performance without him. 

*Created by Jessie Blaeser (<jblaeser2@gmail.com>)*

## Project goal

The goal of this project was to produce multiple visualizations to demonstrate the level of impact Young has on his fellow teammates when they're on the floor together. I aimed to answer the following questions: 
* Does Young make his teammates better? 
* If so, by how much?
* What might be an effective way to measure Young's positive (or negative) imact on his teammates?

## Project notes

To do this, I began by inspecting the [Player Efficiency Rating](http://insider.espn.com/nba/hollinger/statistics) for all players on the NBA, which I scrapped using Beautiful Soup. I also looked at [team efficiency ratings](http://www.espn.com/nba/hollinger/teamstats) to see how the Hawks stacked up — they're ranked second despite a losing record as of February 2022. 

ESPN's John Hollinger's metrics provided an excellent baseline to continue with my analysis. 

From here, I took a look at [NBA.com's 2-player lineups](https://www.nba.com/stats/lineups/traditional/?Season=2021-22&SeasonType=Regular%20Season&GroupQuantity=2&TeamID=1610612737) for the Hawks, which I scrapped using a hidden API on the site (this component can be viewed in the 'etl' folder, in the Scraping NBA.com notebook).

The resulting data required a fair amount of cleaning and fanageling before it was ready for visualization, including: 
* Dropping and renaming columns
* Copying the dataframe on top of itself so as to not leave any pairs out of my later analysis
* Melting the dataframe multiple ways in order to reach desired graphics

From here, I used ggplot/plotnine to visualize components of the Hawks' 2-player statistics. For this analysis, I chose to use: 
* Points: As a baseline, we know Young is the best shooter on the Hawks, but how much better do other Hawks shoot when paired with Young versus other teammates?
* Assists: Young is the teams' point gaurd, and unsurprisingly has the highest assists on the team. But, again, can we visualize how much he improves other players' assists when he is on the floor? Of course, playing with Young will logically move any player's average assists per game up, but by how much? 
* Rebounds: One metric where Young is not the best (as point guards aren't known for getting rebounds). Nevertheless, does his presence on the floor influence others to crash the boards more? 

I've landed on three final graphics, included in the 'viz' folder, that I hope shed light on these questions. However, it's important to note that these results are far from definitive. To properly answer these questions, I would need to run multiple regression analyses to control for compounding variables during gameplay. 


### Data sources

* [ESPN's Player Efficiency Ratings](http://insider.espn.com/nba/hollinger/statistics)
* [ESPN's Team Efficiency Ratings](http://www.espn.com/nba/hollinger/teamstats)
* [NBA.com](https://www.nba.com/stats/lineups/traditional/?Season=2021-22&SeasonType=Regular%20Season&GroupQuantity=2&TeamID=1610612737)