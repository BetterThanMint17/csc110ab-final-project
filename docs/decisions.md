# Decisions
<!-- Claude adds entries during /grill-me and planning. Only the "why did you do it that way?" decisions.
Newest at the bottom. Template:

## D<number>: <short title>
**Decided:** what we chose.
**Why:** the reason, in 1-2 sentences.
**Other options:** what we didn't pick (optional).
-->

## D1: Tic-tac-toe instead of Snake
**Decided:** Build the Arcade Game as tic-tac-toe, with two modes: two local players, or vs. a computer that makes random legal moves.
**Why:** Tic-tac-toe has simple rules and a small fixed board, so it's easy to save and resume. That leaves more time for the parts worth the most points: game history, filters, totals, and explaining the code.
**Other options:** Snake (its moving, growing body makes saving and resuming harder).

## D2: How player names are compared
**Decided:** Names are trimmed and compared ignoring capital letters ("carlos" and "Carlos " are the same player). Blank names are rejected, and so are two players with the same name in one game.
**Why:** Otherwise one person's totals could split into two players, and history filters would miss games.
**Other options:** Exact matching (simpler, but "Carlos" and "carlos" would count as different players).

## D3: First player switches every game
**Decided:** The player who goes first switches every new game, no matter who is playing. Whoever goes first plays X. The app saves who starts next.
**Why:** Fairer than Player 1 always going first, and it only needs one saved value.
**Other options:** Player 1 always first (simplest); switching only when the same two players play again (needs a list of every matchup).

## D4: Quitting a game is a forfeit
**Decided:** Clicking New Game during a game asks "Are you sure? This counts as a loss." If yes, the player whose turn it is loses (in Vs Computer mode, the human). The game is recorded with the result "forfeit". A game with no moves is thrown away and not counted.
**Why:** Stops players from quitting to avoid a loss, and the confirmation stops accidental losses.
**Other options:** Throwing away unfinished games with no penalty; asking who is quitting (more UI to build).

## D5: The computer is a player named "Computer"
**Decided:** In Vs Computer mode the computer is a normal player named "Computer", with its own totals and history filter. Humans can't use that name.
**Why:** Every game always has two players, so the code stays simpler, and "how often does the computer beat me?" is a fun stat.
**Other options:** Not tracking the computer at all.
