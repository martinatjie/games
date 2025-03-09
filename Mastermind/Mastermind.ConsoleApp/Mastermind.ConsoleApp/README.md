# Hello, Mastermind!

Whenever I would go visit my sister, we would play Mastermind. Even at our church bazaar my dad used to prepare a Mastermind game for anyone who was up for the challenge.

Today I decided to code a quick Mastermind game, just to exercise my brain a little.

---

## What we need

- **red pegs** that indicate that a guess is the correct colour and in the right place
- **white pegs** that indicate that a guess is the correct colour but not in the right place
- a **game board** that takes *x** number of **slots** and the same number of options for the game master to add their pegs
- an option to choose **how many guesses** the player has, which will adjust the length of the game board
- the following colour options: .........

---

## Gameplay

### Single Player
The player plays against the computer.
The computer thinks of a random colour combination.

### Two Player
Played via SignalR.

---

## Optional Settings Page

One could expand the game by allowing players to set how many colours they want to play with, how long the colour combination should be that has to be guessed, and how many guesses a player has.

This would also allow for options that aren't colours: e.g. emojis, pictures, letters etc.

## High Score board

This can also be added later.

---

## Let's build it!

*This lends itself very well to a state machine diagram!*

[todo: insert diagram]

Start button
Settings (player should be able to enter a name here too)
Go -> make backend call with FE payload
Load gameboard -> BE sends FE the gameboard data according to settings

enter winning combination / computer chooses winning combi - stored in memory

await input from player, player selects submit or presses enter
combi compared with winning combi
payload returned that shows result & FE fills in the pegs according to the result

play continues like this until...
max guesses reached, in that case game over modal is shown if not won
or
right combi is guessed, in that case fireworks

lastly, score is recorded and stored in permanent storage

back to start button

### Tech stack

This could be built in various different ways but I am leaning towards Svelte, which could then take care of FE & BE.

### Algorithms

#### Naive approach
2 arrays - one for the winning combi, and one for the guess
foreach colour in guess
select array1[x] and check is it equal to array2[x] - this means it's the correct space and colour
if not equal, check if the one array contains the colour of the currently selected item in the other array that is being iterated over


#### Advanced approach
TBC
possibly hashmap, but this game is not very memory or CPU intensive, so we don't have to overcomplicate it with millions of optimisations UNLESS we want to adjust the settings so high that we will eventually run into trouble. Might be cool to test ;-) ... Maybe let the computer be the player...


