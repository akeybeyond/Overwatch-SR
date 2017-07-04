# Overwatch Skill Rating Analysis

Overwatch the popular FPS game by Blizzard like many other popular games with online ladders hides information that can be used by players to improve their ratings. Details are broadly understood, for instance winning increases your skill rating (SR) more than losing. Blizzards calculations for SR are also influenced by individual performance metrics for which the details are not publicly known.

Blizzard's official statement on the matter is that individual performance has little effect upon how much SR a player will gain or lose (and this very well may be true in the grand scale of things). It's important to realize that for the average player being able to gain +30 SR vs + 15 SR is a big deal. Even more so if you might end up losing 20 or more SR compared to losing 10 SR or 15 SR. Therefore it's valuable to player who are wanting to climb the ladder to understand how they can maximize their potential SR gains while minimizing their losses in a way that goes beyond "just win don't lose".

This project seeks to address the problem by using the API provided by owapi.net and the public player data from Overwatch in order to track how players SR changes over time and what factors might play into those increases and decreases. Hopefully this will allow us to identify which factors are most significant in determining individual performance metrics. Of course this will be difficult as SR is ultimately most influenced by who the player wins against or loses too.

In the official statement on SR by Blizzard for Overwatch the system was said to take the probability of you winning or losing and heavily factor that into how much SR you would gain or lose. Winning a game you were not favored to win would result in more SR gain than winning a game the system calculates you winning. Officially the individual performance metric is said to be based upon your performance against the average performance expected given the character you are playing. Of course it could be the case that all factors for the character are weighted equally, That is unlikely since different characters are designed to fill different roles and Blizzard likely wants to promote the intended game styles.

Beacuse of this we can expect that a character designed to be a healer or support would not be judged based upon how many killing blows they are contributing to their team. Rather they might be judged based upon how much healing they are doing. On the other hand the individual performance of a damage focused character might be measured by their ability to get kills and how much damage they are doing throughout the match. As Overwatch keeps data on many aspects of gameplay it's likely that these individual metrics are fairly complex and combine multiple statistics. 

Ultimately the goal is to learn, not just about Overwatch but also about R and Python using both tools to pull, combine and analyze our data.

## Stage 1: Collecting Data

OWAPI uses Python to pull the data from the Overwatch player profiles into JSON allowing us to easily manipulate and collect large amounts of information. Initially we will focus on Torbjorn and we will be collecting data on 50 players at a variety of skill ratings selected from a list who commonly play the character.

## Stage 2: Processing Data

We will have to check the data for any missing information, while this is expected to be minimal there may be some cases in which the data is formatted in correctly. For Torbjorn specifically data for his armor is stored in two different variables but will need to be combined into one. Also not all of the information we will pull is relevent, for instance we will not have much use for information on medals as they compare the player to the other players on their team not to other players on the character. Therefore they will not be of much use in trying to understand the factors that influence SR.

## Stage 3: Analysis

Currently the plan is to start by creating graphical representations of the interactions between SR and the other factors. We may also want to try to remove the influence of winning, by looking into what factors influence winning heavily. This will be difficult as in many cases the factors that influence winning would also make sense to put into a measure of individual performance. Therefore we will have to accept this problem, but we can still keep it in mind. Also we may find that there are factors that heavily influence SR that are not correlated positively with winning. A recent issue has been that players felt that Mercy's (a support in OW) performance metric was too heavily influenced by how many players you could ressurrect with your ultimate. This led to Mercy players waiting until their team had died to resurrect rather than resurrecting key members in fights in order to maximize the chance of winning. 

