---
date: 2025-02-25T11:25:05-04:00
description: "An analysis of how getting certain letters during a Scrabble game impact the outcome. Based on 64 two-person games."
featured_image: "images/scrabble/scrabble-header.jpg"
tags: []
title: "Scrabble: what letters lead to a win?"
disable_share: false
summary: "IN PROGRESS - An analysis of how getting certain letters during a Scrabble game impact the outcome"
---

Overview:

* 64 Scrabble games were recorded between myself and my boyfriend (2-player games only) between December 2019 and February 2025 (_yes_, this means that the sample size is very small)

_______________________

_This analysis is currently in progress_
__________________________________

Context:

* My boyfriend and I bought a French Scrabble game in 2019. The French game has seven high-scoring letters: J (8), K (10), Q (8), W (10), X (10), Y (10), and Z (10). We played the game in English.
* Scrabble became a pastime for us during the pandemic. Fifty games were played in 2020 alone.
* I kept track of the dates we played, who started the game, who won the game, the final scores, and who had each of the seven high-scoring letters. 
* I did not keep track of what letters were left over at the end of the game and therefore what scores were added and subtracted from final scores. In future, I would add this to the data in order to analyse the most common ending letters/points, to find out if that impacts the overall winner more than not, and to see who most often gets stuck with letters at the end.
* I also did not track the order in which the letters were chosen. In future, I would add this as well as it could be interesting to see how order impacts scoring and winning (e.g., I hypothesize that getting a Q during the last turn would have a negative impact on score).
_______________________

Questions:
1. Which high-scoring letters most often lead to a win for each of us? Which letters most often lead to a loss?
2. What combination of letters most often leads to a win for each of us? What combination of letters leads to a loss more?
3. Does starting have an impact on the outcome of the game for each of us? Does starting have an impact on score?
4. And most importantly, how many points is each letter responsible for? In other words, while playing the game, can I anticipate an increase or decrease in a certain amount of points based on which letters I get?
5. Similarly to the above question, how do the odds of winning change for each letter? In other words, while playing the game, can I anticipate a higher or lower chance of winning depending on which letters I get?

**I have organized this project into sections based on some preliminary figures, the questions above, and a section at the end diving into the three tied games.**

For the remainder of this project, I am referred to as "M" and my boyfriend is referred to as "S".
_______________________

**Preliminary analysis and visualizations**

We mostly played throughout the pandemic, resulting in the vast majority of games in 2020.

![Count of games by year](/images/scrabble/GamesByYear.png)

Looks like we were really crazy about it in January 2020 specifically!

![Count of games by month](/images/scrabble/GamesByMonth.png)

I won 37 games, S won 24 games, and there were 3 ties

![Overview of Scrabble games won](/images/scrabble/CountOfWon.png)

Unfortunately, six games had incomplete data on who had which letters. 

I got at least four of the seven high-scoring letters in 34 out of the 58 games remaining, while S had at least four of those letters in 24 games. I had at least five of the seven high-scoring letters in 16 games, while he had at least five of the letters in 14 games - much more comparable. I had all seven high-scoring letters in only one game, while S never got all seven.

The chart below shows the number of games played where I had anywhere from 1-7 of the high-scoring letters.

![Number of letters that I had histogram](/images/scrabble/NumLettersHist.png)

We got each letter between 26 and 33 times in those 58 games. No remarkable insights here, although S got Z much more often than I did.

![Counts of games in which we got each letter](/images/scrabble/CountsOfLetters.png)

_______________________

**1. Which high-scoring letters most often lead to a win? Which letters most often lead to a loss?**

_In this section, I am looking at the 58 games with complete data only._

First, a quick look at the win rates associated with each letter. For this part, I looked at whether the presence of a letter was associated with a win or loss. For example, if there was a game where I had a J and I won, that would count as a win for J. If there was a game where I had a J and I lost, that would count as a loss for J. 

Below is a chart showing the percentage of wins when the winner had each letter. Y had the highest win percentage of over 65% (meaning that when one of us had Y, that person won the game over 65% of the time - 38 games). Z had the lowest win percentage of almost 47%, and Z and J were the only letters associated with a win percentage of less than 50%. This could indicate that getting Z and J leads to a slightly less than random chance of winning - but more on this later in section xx.

![Total win percentage associated with each letter](/images/scrabble/LetterWinPercsTotal.png)

The chart below shows the percentage of wins when S had each letter. Again, Y had the highest win percentage of almost 61%. Z and J had the lowest win percentage of 40%, and Z, J, and Q were the letters associated with a win percentage of less than 50%. 

![S's win percentage associated with each letter](/images/scrabble/LetterWinPercsS.png)

And the below chart shows the percentage of wins I had with each letter. Interestingly, the letter with the highest win percentage for me was W, with K and Y not far behind. This could mean that I am simply better at using W and K than S is. None of the letters I get are associated with a win rate lower than 50%, which indicates that getting any of these letters increases my odds of a win. The letters I get that have the lowest win rate are J and Z.

![My win percentage associated with each letter](/images/scrabble/LetterWinPercsM.png)

To visualize the how win rates differ between S and me, the chart below shows how getting each letter impacts the odds of winning - a negative percentage shows the odds dropping when compared to random chance (50%), and a positive percentage shows the odds increasing when compared to random chance.

xx - redo chart in Python
![My win percentage associated with each letter](/images/scrabble/WinPercsDiffRandom.png)

**2. What combination of letters most often leads to a win for each of us? What combination of letters leads to a loss more?**

_In this section, I am again only looking at 55 games: the games with complete data and those with a winner - no ties._

I identified the 129 possible combinations of 0, 1, 2, 3, 4, 5, 6, and 7 letters that each of us could have had. Out of those 129 combinations, we had only 80 different combinations between us. There were only 24 combos that appeared at least twice in the data. Using these 24 combinations of letters (including two single letters, J and K), I calculated the win percentage overall for each, similarly to how I did above. The label includes the percentage as well as the number of won games.

![Total win percentage associated with each letter combination](/images/scrabble/CombosWinPercTotal.png)

Note that the sample size here is so small that we can't really draw any major conclusions - this whole analysis is just for fun! However, we can see that the more letters a player has, the higher the win rate. When a player had only one letter, they had a 0% win rate. If I had a larger dataset with more rows with each combo, I might be able to come to the conclusion that, for example, I have a 67% chance of winning if I get the letters J, X, Y, and Z during a game.

For S, there were a few combinations that always led to a loss, but there were also a few that always led to a win - see the chart below.

![S's win percentage associated with each letter combination](/images/scrabble/CombosWinPercTotal-S.png)

I AM HERE




Percentages are great, but I wanted to do more in-depth analysis to understand the impact of each letter on the game outcome. I chose binary classification as the method here, so I started with the 58 games that have complete data and further removed the three games that ended in a tie. For the sake of this analysis, I determined that the positive class would be games I won. Each letter column was then transformed into 1s (if I had the letter) or 0s (if S had the letter).

Because each column is also binary (and represents a count), I started with a Poisson binary classification.

binary classification

[]




__________________________________

**Final thoughts:**

* It felt like we played Scrabble way more than 64 times in five years




