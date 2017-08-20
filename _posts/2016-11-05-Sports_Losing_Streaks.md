---
layout: article
title: "Sports Losing Streaks"
description: "Some simulations on the frequency of losing streaks and title droughts in sports."
date: 2016-11-05 12:00:00 -0600
category: Simulation
tags: [Simulation, Sports, Baseball, Probability, Title Drought, Losing Streak]
comments: false
image:
  teaser: Sports-400x250.png
modified: 2016-11-07 12:00:00 -0600
---

An article about losing streaks and title droughts in sports.

# Losing Streaks and Title Droughts in Sports #

I adopted the [Chicago Cubs](https://en.wikipedia.org/wiki/Chicago_cubs) as my favorite baseball team many years ago when I went to school in the Midwest, mostly because my friends there grew up watching the Cubs.  I've managed to take in a couple of games at Wrigley Field, too, while drinking a few [Old Style's](https://en.wikipedia.org/wiki/Pabst_Brewing_Company#Old_Style).  So, it was amazing to watch the Cubs win this week in the most incredible baseball game I have ever watched.  I think I went into cardiac arrest a few times over the last few innings.  Now that they've won and their 108 year losing streak has been broken, being the computer and stats nerd I am, I found myself wondering just how rare a 108 year losing streak is, given the number of teams in [Major League Baseball (MLB)](https://en.wikipedia.org/wiki/Major_League_Baseball).  So, I decided to create a [Jupyter](https://en.wikipedia.org/wiki/IPython#Project_Jupyter) notebook to find out.  If you want to run your own scenarios, the notebook is available on my github [here](https://github.com/diffusioned/Python-Code/blob/master/SportsLosingStreaks.ipynb).  If you want to run a new simulation of this, I use the [Anaconda](https://www.continuum.io/) Python distribution as it's free and open source.  You can see a static version of this notebook using [this link](https://nbviewer.jupyter.org/github/diffusioned/Python-Code/blob/master/SportsLosingStreaks.ipynb).  Note, the values there differ from the ones I used to write this post.

## Randomness and Uncertainty ##

We humans are terrible at confusing truly random numbers with what could be called numerical [entropy](https://en.wikipedia.org/wiki/Entropy), i.e. the numbers should be all mixed up and evenly spread out.  What do I mean?  If you ask someone what a sequence of 15 random numbers between 0 and 9 would look like, you would see something like:

3, 4, 9, 1, 2, 0, 4, 5, 7, 3, 9, 6, 0, 3, 2

In fact, when I wrote that sequence just now I paused in the middle and looked back to see what number hadn't appeared yet, yet I still left out the number 8.  If you ask a computer to output 15 random digits form 0 to 9, which I did, you'll see a sequence like this:

0, 4, 3, 4, 1, 9, 1, 3, 1, 1, 3, 2, 5, 0, 6

In this sequence, the number 1 appears four times, and the numbers 7 and 8 don't appear at all.  If I kept asking the computer for another sequence, I'd eventually see a sequence of three repeated digits, since the odds of the number 7, say, appearing three times in a row is 1 in 10<sup>3</sup> or 1 in 1000 (the number 777).  Another example could be lottery numbers.  If you grab someone off the street and ask them what tonight's lottery numbers are likely to be, you would get something like:

6, 19, 28, 33, 39, 42

If you ask why didn't they chose 1, 2, 3, 4, 5, 6 you'd probably get a crazy look and a comment along the lines of, "That will never happen!!"  Yet these outcomes have the **exact, same probability**.  Humans have difficulty with probabilities and random events, and we often fool ourselves with beliefs and tendencies that have been identified and named, such as the [hot-hand fallacy](https://en.wikipedia.org/wiki/Hot-hand_fallacy), where we believe that if someone performs a feat of skill successfully multiple times in a row, they will suddenly be *more likely* to repeat this task (see [NBA Jam](https://en.wikipedia.org/wiki/NBA_Jam)).  Conversely, we also have the belief that if a particular event hasn't arose in a while, then it is *more likely* to occur, which is known as the [Gambler's fallacy](https://en.wikipedia.org/wiki/Gambler's_fallacy), i.e. "He's 0 for 4 so he's due for a hit!"  These beliefs appear to be the opposite of each other, so it's easy to see how these can be labeled as fallacies since it's improbable for both phenomena to occur at the same time.  We can relate these two beliefs to sports losing streaks.  Our hot-hand fallacy could be interpreted in negative way, such as "we haven't won the championship in 100 years, so we're never going to win", and rationalizing this belief with various jinxes and [curses](https://en.wikipedia.org/wiki/Curse_of_the_Billy_Goat).  Conversely, our expectation that we should have won by now can be related to the gambler's fallacy.  "We haven't won in 65 years, it has to be our time"

When we look at our chances of winning *strictly* from randomness, each club in the MLB, NBA, or NHL has a 3.33% chance of winning the championship every year, based on a total number of 30 teams in each league.  For the NFL and its 32 teams, that drops to 3.12%.  This would mean *on average* our team should win the championship about once every 30 years.  Based on that statistic, if our team hadn't won in say, 50 years, we might feel like we're cursed, let alone 100 years or more.  Now that the Cubs have won the title, the largest drought between World Series victories is 68 years to the Cleveland Indians, which is the team the Cubs beat in 2016.  The next six longest droughts are teams have never won the title, which are the Texas Rangers, Houston Astros, Milwaukee Brewers, San Diego Padres, Washington Nationals, and the Seattle Mariners.   These teams only joined the league in the 1960's and 70's, so it's unfair to compare these values to teams that have been in much longer.  There were also two teams that haven't won a title, the Colorado Rockies and Tampa Bay Rays, but these teams only joined in the 1990's.  To be fair (or unfair) to all 30 of our teams, let's simulate a century worth of seasons and see what happens.

## Batter up! ##

Our simulation of each season is based on a uniform probability distribution - each team has an equal chance of winning the title.  We are assuming here that all events over a season are completely random and average out over time.  Considering that baseball does not have a [salary cap](https://en.wikipedia.org/wiki/Salary_cap) and some teams' payrolls can be 3, 4, or 5 times the others, perhaps larger market teams such as New York and L.A. could have a distinct advantage over time versus other teams.  If you'd like to test this and are handy with Python, you could add in normalized probabilities for each team to the notebook.  If we are testing 100 years, we would expect each of our teams to win an average of 3.33 championships (100/30).  Let's look at the results of our century simulation:

	Number of Victories for each team over 100 years
	Arizona Diamondbacks:  0
	Atlanta Braves:  1
	Baltimore Orioles:  1
	Boston Red Sox:  5
	Chicago White Sox:  2
	Chicago Cubs:  4
	Cincinnati Reds:  2
	Cleveland Indians:  5
	Colorado Rockies:  0
	Detroit Tigers:  1
	Houston Astros:  5
	Kansas City Royals:  2
	Los Angeles Angels:  7
	Los Angeles Dodgers:  3
	Miami Marlins:  4
	Milwaukee Brewers:  3
	Minnesota Twins:  6
	New York Mets:  4
	New York Yankees:  2
	Oakland Athletics:  0
	Philadelphia Phillies:  2
	Pittsburgh Pirates:  4
	San Diego Padres:  6
	San Francisco Giants:  2
	Seattle Mariners:  4
	St. Louis Cardinals:  2
	Tampa Bay Rays:  6
	Texas Rangers:  7
	Toronto Blue Jays:  5
	Washington Nationals:  5

Our distribution of the number of team victories definitely does not reflect a uniform distribution.  While two teams won 7 times, three teams only won once and our fans in Arizona, Colorado, and Oakland did not see a title victory in this century!  We can also look at the longest losing streak for each team.  Note, my simulation also counts the time from beginning and endpoints, so if your team won a title in year 10 and year 20, your title drought at the end of the century would be 80 years (100-20).

	Longest title drought for each team over 100 years
	Arizona Diamondbacks did not win at all
	Atlanta Braves : 50
	Baltimore Orioles : 67
	Boston Red Sox : 32
	Chicago White Sox : 45
	Chicago Cubs : 58
	Cincinnati Reds : 90
	Cleveland Indians : 44
	Colorado Rockies did not win at all
	Detroit Tigers : 50
	Houston Astros : 33
	Kansas City Royals : 49
	Los Angeles Angels : 30
	Los Angeles Dodgers : 39
	Miami Marlins : 49
	Milwaukee Brewers : 48
	Minnesota Twins : 45
	New York Mets : 37
	New York Yankees : 45
	Oakland Athletics did not win at all
	Philadelphia Phillies : 81
	Pittsburgh Pirates : 43
	San Diego Padres : 25
	San Francisco Giants : 82
	Seattle Mariners : 53
	St. Louis Cardinals : 73
	Tampa Bay Rays : 42
	Texas Rangers : 31
	Toronto Blue Jays : 38
	Washington Nationals : 49

On average, each team should win the title every 30 years, yet only one team had a title drought under 30 years (the Padres with 25) and one team (the Royals) had a title drought of exactly 30 years.  We can compare these values to the average human lifespan of, say, 80 years, and now see that six of our teams had droughts over this average lifespan.  No wonder our fans feel cursed!  These results show just how long a number with a probability of 1 in 30 can take to appear.  Perhaps we humans just don't have a reference to compare an everyday occurrence of 1 in 30 as opposed to a coin flip (1 in 2), for example.

Let's expand our sample size to a millennium and get all of our teams at least one victory.  As we run the simulation out to 1000 years, we are giving more chances for each team to win.  In this simulation, we will have an average value of 33.3 victories (1000/30) for each team:

	Number of Victories for each team over 1000 years
	Arizona Diamondbacks:  35
	Atlanta Braves:  29
	Baltimore Orioles:  37
	Boston Red Sox:  40
	Chicago White Sox:  32
	Chicago Cubs:  37
	Cincinnati Reds:  27
	Cleveland Indians:  35
	Colorado Rockies:  35
	Detroit Tigers:  31
	Houston Astros:  28
	Kansas City Royals:  32
	Los Angeles Angels:  28
	Los Angeles Dodgers:  29
	Miami Marlins:  42
	Milwaukee Brewers:  38
	Minnesota Twins:  31
	New York Mets:  37
	New York Yankees:  36
	Oakland Athletics:  24
	Philadelphia Phillies:  29
	Pittsburgh Pirates:  36
	San Diego Padres:  38
	San Francisco Giants:  30
	Seattle Mariners:  30
	St. Louis Cardinals:  41
	Tampa Bay Rays:  33
	Texas Rangers:  26
	Toronto Blue Jays:  36
	Washington Nationals:  38

That's better!  Over a millennium, the lowest number of total victories was 26 and the highest, 42.  Now for the downside.  We increased the number of seasons to try and get all of our teams some championships.  However, as the number of seasons increase, we are *more likely* to see longer droughts where a number doesn't come up.  Here are the millennial results for title droughts:

	Longest title drought for each team over 1000 years
	Arizona Diamondbacks : 114
	Atlanta Braves : 149
	Baltimore Orioles : 88
	Boston Red Sox : 68
	Chicago White Sox : 114
	Chicago Cubs : 145
	Cincinnati Reds : 102
	Cleveland Indians : 137
	Colorado Rockies : 125
	Detroit Tigers : 126
	Houston Astros : 104
	Kansas City Royals : 94
	Los Angeles Angels : 121
	Los Angeles Dodgers : 151
	Miami Marlins : 95
	Milwaukee Brewers : 101
	Minnesota Twins : 139
	New York Mets : 61
	New York Yankees : 77
	Oakland Athletics : 143
	Philadelphia Phillies : 165
	Pittsburgh Pirates : 98
	San Diego Padres : 81
	San Francisco Giants : 255
	Seattle Mariners : 125
	St. Louis Cardinals : 74
	Tampa Bay Rays : 98
	Texas Rangers : 172
	Toronto Blue Jays : 117
	Washington Nationals : 115

Oh no!  In this particular scenario, we have many teams that saw a title drought of over 100 years, and please spare a thought to our San Francisco Giants fans who had one stretch where they didn't win the title for 255 years!

While these results may seem depressing, they do show that, going forward, a title drought of over 100 years might not be all that rare and there will be no need to feel that your team is "cursed".  However, how many folks are going to want to shell out for season tickets knowing that their team won't win for the next century?  Of course, the uncertainty and the high drama in every game is what we live for in sports, and we all want to believe that this year will be **our year**.  This post does show why it's important to have a parade and break out the champagne when *your* team wins.

*Note*: The team names used here are all trademarks of [Major League Baseball](http://mlb.com).