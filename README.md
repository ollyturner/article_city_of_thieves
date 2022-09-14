# City of Thieves solved

## Abstract

City of Thieves is a text adventure in the form of a book.
To beat it, a player has to make the right choices, in a stochastic environment.
The optimal strategy to beat this game is unknown,
yet according to author the effect of stochasticity is low.
Here we show the optimal strategy to beat this game
for different amounts of luck involved.
[prime result here].

## Introduction

> The one true way involves a minimum of risk and any player, 
> no matter how weak on initial dice rolls, should be able to get through fairly easily. 
>
> Ian Livingstone

### Adventure books

In the 1980's, before the era of computing, adventure books
allowed the reader to partake a fictional adventure.
Adventure books consisted of hundreds of short chapters in
a random order. The reader starts at chapter 1 and is asked
to do one of multiple actions. Each action takes the player
to a next chapter. The player ultimately completes the game
or dies.

### City of Thieves

![](Ff5puffin.jpg)

> Cover of the first edition of 'City of Thieves'

City of Thieves is a an adventure book written by Ian Livingstone in 1984,
in which the player ventures to the castle of the protagonist,
after having visited a certain person in a medieval city,
the titular 'City of Thieves'. 

### Premise

In summary, with the game there are three characteristics
the fictional character can have,
which are determined from dice rolls.
According to the quote of the author at the start of the article,
a player should be able to succeed 'no matter how weak on initial dice rolls'.
This research challenges that statement,
as anekdotal evidence suggests otherwise.

### Game rules

#### Three statistics description

A character has three statistics: health, skill and luck. 
More health allows a player to take more damage,
for example, taking hits in combat.
More skill allows a player to be better in combat,
as well as succeed in certain situations, 
for example, when forcing open a door with one's shoulder.
More luck allows a player in a situation that requires luck,
for example, when an arrow trap springs, luck may let the player 
avoid the (lethal!) arrow.

#### Three statistics dynamics

These three statistics can be modified within the game.
Health can be increased by certain items, such as food. 
Health decreases when taking damage, which is usually in combat,
but can also stem from other physical injuries, such as falling down a wall.
Skill can be increased by certain items, such as a better sword.
Skill can be decreased by other such items, such as cursed gloves that
decrease the dexterity of the wearer.
Luck can be increased by certain events or items, 
such as hearing a blessed song.
Luck decreases mostly by using it (see below) or by certain events, such as 
killing one of the key characters.

#### Three statistics initialization

The game starts with a character generation session, 
similar to most RPGs.
For one or more times, 4 dice are rolled.
In a pre-defined order, the dice values determine the
player's characteristics.
A player's skill equals the first dice roll value plus three (this 
deviates from the game, see 'Discussion'), the condition is the sum of two dice rolls,
where luck is the last dice roll value plus six.
The player may roll as often as possible, allowing to get the best values,
but this is quite dull.
As stated earlier, according to the author, the adventure is constructed in such
a way, that these dice rolls are of less importance. 
This research investigates the impact of these dice rolls (Hypothesis 0).

#### Potions

After the character generation session, a player may pick
one of three potions, for either of the three statistics.
Where the health and skill potion refresh their respective value
to the initial value, a luck potion does so, as well as add one additional 
point. It is an open question, which potion is best to pick
This research investigates the impact of picking each of these potions (Hypothesis 1).

#### Initial inventory

At the start of the game, the player starts with 3 items (including
the chosen potion), 30 gold coins and 10 provisions. 
These items may be lost or sold. 
The gold coins are used as a currency, to buy items or other situations,
such as bribing a guard.
The provisions allow a player to increase his/her health.

### Types of chapters

Within the actual game, there are multiple kinds of chapters.
The most common type of chapter is to pick one of multiple
actions. Sometimes some actions can only be picked after having
acquired a certain item, for example throwing a lantarn at a hostile mummy. 
The other types of chapters
are fighting chapters, logical chapters, luck chapters and skill chapters.

#### Fighting chapter

In a fighting chapter, the player fights one, two or three opponents.
All opponents have a know value for their health and skill, that
are similar to the player. The goal of the player, is to 
succeed in combat, by bringing down the health of opponents to zero.
Likewise, when an opponent hits the player, its health goes down,
where a health of zero ends the game. 
A player can use luck to increase the damage dealt to the enemy,
or to decrease the damage dealth by that enemy. Using luck decreases its
value, decreasing the change of a positive event in successive usages. 

#### Logical chapter

A logical chapter is simply a conditional statement
regarding the possession of an item. For example, when the
player leaves the city, he/she needs to possess some key items,
else the game is over.

#### Luck and skill chapters

Luck and skill chapters are similar: a player needs to roll the dice
to test his/her skill or luck, after which a different chapter follows
depending the success of this. 
An example of a skill chapter is a game where the player plays a game 
of pricking a dagger between his/her fingers as quickly as possible.
An example of a luck chapter is when a snake tries to bite the player. 
The only additional difference is that using luck decrease that statistic.

### Progression

The adventure starts at the gates of the city, the first city
streets, a bridge at which a vital character lives, some more city streets,
after which the city is left. If the player has acquired some esstial items,
the adventure goes through a forest, followed by the keep of the protagonist.
The story always go forwards, that is each location can only be visited once,
as the player cannot venture back.
There is only location (the keep's 2nd and 3rd [check] floor) in which
a location can be visited multiple times, but doing so is either
neutral or detrimental.

#### Cannot go back

Because the player cannot go back and the player needs to acquire some
essential items, some decisions cause the player to lose the game due to
this. For example, at the first junction after crossing the bridge,
the player must go towards the [name] street to acquire such a key item,
after which the game takes the player back to follow the other street 
afterwards. Therefore, reaching the latter location on itself is uninformative:
only with the key item acquired the player has a change of winning the game.
The state transition, however, is informative: going from that 
junction directly to the final destination (without getting the
key item) is a sure fail.

#### The first junction

Upon passing the city gate, there is junction, in which the player
has to choose one of three streets. None of these streets contain an
essential item and all lead to the same bridge. Yet, these three routes
vary in the items a player can find as well as the amount of danger.
It is unknown which of these three streets results in the
highest chance of success.
This research investigates which of these three roads gives the highest
probability of finishing the game (Hypothesis 2).

### Conclusion

This research answers all the questions a player of 'City of Thieves'
may have, solving one more puzzle that has plagued humanity for decades.

## Hypotheses

 * H_0: the dice rolls at the start of the game do not influence the
   chance of winning the game, when the game is played optimally
 * H_1: the potion picked at the start of the game do not influence the
   chance of winning the game, when the game is played optimally
 * H_2: it does not matter which of the three streets is picked at the initial
   junction for the chance of winning the game, when the game is played optimally

## Methods

To allow the game to be solved by a computer, it has been converted
to a computer game. 

To conclude what the optimal strategy is,
Q-learning (a type of reinforcement learning) is used,
as this type of unsupervised learning assigns the value
of each state numerically, allowing for comparison between,
for example, good and mediocre states.

To answer H_0 and H_1, we measure the chance to win the game, when played
optimally, for the different initial statistics and potion. 
The probability of winning the game is simply set to be the
value of the initial state.
If all chances
are all equal, H_0 and H_1 is accepted. If chances differ between the
different statistics, H0 is rejected. If chances are all identical, yet
differ per initial potion, H_1 is rejected.

To answer H_2, we measure the payoff the optimal stategy assigns to
arriving at either of the three streets. 
If these payoffs are equal, H_2 is accepted,
else H2 is rejected.

## Results

![](fig_1.png)

> Figure 1: the chance to win the game when played optimally,
> for the different initial statistics
> and initial potion.
> Colors denote this chance, from red (0%) to green (100%) [let the
> plotting algorithm decide]

[Example reasoning] As can be seen in figure 1, there are different probabilies to win
the game regarding the initial dice rolls. Therefore, H_0 is rejected.
Instead, [interpret]

[Example reasoning] As can be seen in figure 1, there are different probabilies to win
the game regarding the initial choice of potion. Therefore, H_1 is rejected.
Instead, picking a [some] potions gives the highest chance of success.

![](fig_2.png)

> Figure 2: graph of the game, in which the nodes are the chapters,
> and edges denotes the possible actions. The number within the node
> denotes the chapter number as used in the book. The value next to each
> edge denotes the expected payoff. Node 1 is the starting chapter,
> where node 74 is the focal junction. The transitions between nodes 1 and
> 74 are summarized by a grey rectangle. Target nodes are Clock Street (17), 
> Market Street (116) and Key Street (95).

[Example reasoning] As can bee seen in figure 2, our algorithm assigned different 
payoffs going from the junction (74) to [location] ([number]). Therefore, H_2 
is reject. Instead, selecting to go to [location] is part of the optimal 
strategy.

## Conclusions

## Discussions

There are some minor deviations from the book:

In the character generation, a player's skill equals the first dice roll value 
plus three, where in the book, one is allowed to add six to the dice roll 
instead. This difference is due to consistency and results in the
same behavior: the book ignores that the initial armor and sword of the
player are already accounting for three skill points. These values are
known because in chapter 408 the starting armor is lost (2 skill points)
and in chapter 126 the starting sword is lost (1 skill point). 

Chapter 130 has a fight that has a maximum number of rounds.
In the current implementation of the game, this fight has
an indefinite number of possible rounds, similar to any regular fight.
Because the optimal strategy avoids this fight, we expect this has no
consequence on our conclusions.

## Acknowledgements

RJCB was the main writer of the manuscript.
RJCB rewrote the book as a text adventure, 
together with Jeroen Niemandal, Carmen IJsebaart
and Greg Fivash.

## Images

Cover of the first edition, featuring art by Iain McCaig, 
from [https://en.wikipedia.org/wiki/File:Ff5puffin.jpg](https://en.wikipedia.org/wiki/File:Ff5puffin.jpg)

## References

 * [Giddings, 2006] Giddings, Seth. Walkthrough: Videogames and technocultural form. Diss. University of the West of England, Bristol, 2006.
 * [Livingstone, 1984] Livingstone, Ian. City of Thieves. No. 5. Dell Pub Co, 1984.
