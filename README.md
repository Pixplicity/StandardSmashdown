Standard Smashdown
=================

This page contains the official specification for Standard Smashdown Ping-Pong (formerly Polish Roulette) as developed by Pixplicity et al.

In its popularity, we've seen that there has been increasing fragmentation in the rules of play, even new, non-standard additions to the rules. To restrict the gameplay to a base set of rules, we've introduced **Standard Smashdown**. With this set of formal specification and test suites, you can make sure you implement your gameplay according to spec!


## What is Smashdown?

Smashdown is a variant of multiplayer ping pong for an arbitrary number of players, based on conventions used from conventional ping pong. It was developed in august 2014 by Henoch van Paesschen and Eric Lammertsma, who played the first game of rules together with a few others, and it soon became largely popular in the office building. By september 2014 there were a variety of rules amidst different players.


## Why is a spec needed?

Henoch van Paesschen's original Smashdown rules does not specify the gameplay unambiguously.

In the absence of a spec, early implementers consulted the original Smashdown rules to resolve these ambiguities. But keeping track of points was quite buggy, and gave way to teaming up against winning players in many cases, so it was not a satisfactory replacement for a spec.

Because there is no unambiguous spec, implementations have diverged considerably. As a result, users are often surprised to find that a game that is at Pixplicity, plays differently at another office (say, the awarding of points). To make matters worse, because you can't “win” at Smashdown, the divergence often isn't discovered right away.


### How to play

Standard Smashdown is developed to allow any number of players above 4 to play simultaneously at a single table without running around it. At any given moment there are only 4 active players at the table, at the regular position as if they were playing doubles.

![Player position indications for Standard Smashdown](https://i.imgur.com/As0zVoN.png)

The player at position `A` serves the first ball. The ball should be returned by player `C`, then player `B`, then `D` followed again by `A` (and so on). Whenever a point is scored, the losing player leaves the table and the empty spot is filled by the other players by shifting clockwise until quadrant `A` is vacant. A new player that was waiting before now joins the game from quadrant `A` and gets to serve. The losing player takes their place at the end of the waiting line.


### Keeping Score

In Standard Smashdown, each player plays for themselves. Scores are individual, and therefore each player is required to keep their own score.

* When a point is scored (the way one would could in regular tabletennis play), each active player receives one point, with the exception of the losing player.
* The losing player loses all their points.
* Players in line do not receive points, this includes the player first in line who enters spot `A`.
 
Example: player B plays a ball that D is unable to return. Player A, B and C each score a point and move on to their adjacent spots. Player D loses all their points. The new player at `A` starts with zero points.

Due to this method, the player at `D` always has the highest score.


### The official Standard Rules for Smashdown Ping-Pong

The official rules are currently at discussing. Common opinion has reached a consensus that it is not allowed to hinder other players by e.g. getting in their way, or by hitting 'easy' balls that other players can use to eliminate an opponent, with the following exception:

_When the player at position `D` reaches a score of ten or higher, the player at `C` gets permission to serve 'easy' balls to player `B` in order to attempt elimination of `D`_.

This part is at discussion, however, and rules are being experimented with to discourage this behavior.


### Licensing

We invite everyone to play Standard Smashdown and to create, adapt or reject its rules and regulations. Tell us what works, what doesn't, or why we should call it *Common Smashdown* or *Strict Smashdown* instead.
