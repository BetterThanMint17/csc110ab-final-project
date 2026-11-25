# Project Proposal

**Name:** Carlos
**Project:** Arcade Game (Tic-tac-toe)
**App name:** <!-- pick once you choose a theme -->
**Repo link:** https://github.com/BetterThanMint17/csc110ab-final-project

## My idea in two sentences
A tic-tac-toe game where two people can play each other on one computer, or one person can play against the computer.
It keeps a record of every finished game so players can look back at their results and see their win/draw/loss totals.

## My twist / theme
Not decided yet. I'm thinking about a theme with custom pieces instead of plain X and O, plus a leaderboard of
player names. I'll pick the theme before the UI prototype (due Mon Nov 30).

## Requirements checklist
- [ ] Correct rules and visible game state: legal moves only, alternating turns, row/column/diagonal wins, and draws
- [ ] Two modes: two local players, or a computer opponent that makes legal moves
- [ ] Restart without deleting past results
- [ ] Record of completed games: player names, mode, result, and move history
- [ ] Filter past results by player or by mode
- [ ] Review the moves of a past game
- [ ] Calculated win/draw/loss totals, counting each completed game once
- [ ] Reject bad input with clear messages (e.g. a square that's already taken, blank player names)
- [ ] Save and reopen the unfinished game and past results, including everything needed to make the next move
- [ ] Data stored in classes/objects and `ArrayList`s

## The 60-second demo I imagine
I type in two player names and play a quick game, and the app shows whose turn it is and announces the winner.
Then I switch to "vs. Computer" mode, make a couple of moves, and close the app in the middle of the game.
When I reopen it, the game is right where I left it. To finish, I open the game history, filter it by one
player, look at the moves of an old game, and show the win/draw/loss totals.

## Stretch goals (if time allows, in this order)
1. Replay a past game step by step (move 1, move 2, ...)
2. A bigger board (4×4)

## My biggest worry
Kind of everything about it: I haven't built a GUI, saved to files, or made a project this big before.
