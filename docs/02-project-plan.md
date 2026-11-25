# Project Plan
Tic-tac-toe (Arcade Game). Due Mon Nov 30. Final submission + demo Wed Dec 9.

## Requirements → features
| Requirement (official) | Feature(s) | Priority |
|---|---|---|
| Correct rules: legal moves, alternating turns, row/column/diagonal wins, draws | F1 Play a game | Must |
| Visible game state | F1 Play a game (board + status line: whose turn, winner, draw) | Must |
| Two modes: two local players or a computer making legal moves | F2 Start a game, F3 Computer opponent | Must |
| Restart without deleting past results | F4 New game / forfeit | Must |
| Record of completed games: names, mode, result, move history | F5 Game history | Must |
| Filter results by player or mode | F6 Filter history | Must |
| Review a game's moves | F7 Review moves | Must |
| Win/draw/loss totals, each completed game counted once | F8 Player totals | Must |
| Reject bad input with clear messages | F1, F2 (taken square, blank/duplicate/reserved names) | Must |
| Save and reopen unfinished game + past results, enough to resume the next move | F9 Save and reopen | Must |
| Data in classes/objects and `ArrayList`s | All (one manager class owns the lists) | Must |

## Rules I decided
- **Board:** 3×3. A move is legal only on an empty square while the game is still going.
- **Win / draw:** 3 in a row (row, column, or diagonal) wins. A full board with no winner is a draw.
- **Who goes first:** switches every new game, no matter who is playing. Whoever goes first plays **X**. (D3)
- **Computer:** picks a random empty square. If it goes first, it moves right away when the game starts.
- **"Computer" is a player** with its own totals and its own history filter. Humans can't use the name "Computer". (D5)
- **Names:** trimmed, case doesn't matter. Blank names and two identical names in one game are rejected. (D2)
- **Quitting (forfeit):** clicking New Game during a game asks "Are you sure? This counts as a loss." If yes, the
  player whose turn it is loses (in Vs Computer mode, the human). A game with no moves is thrown away and not
  counted. Forfeits are recorded with the result "forfeit". (D4)
- **Totals:** each completed game (win, draw, or forfeit) is counted once, for both players. Unfinished games don't count.
- **Saving:** one unfinished game at a time. It saves automatically after every move and when a game ends.
  If the save file is missing, the app starts with empty history. If a line is broken, it skips that line.

## Features by priority
### Must (needed for requirements)
- [ ] F1 Play a game: click squares, turns alternate, detects win/draw, rejects taken squares and moves after the game ends
- [ ] F2 Start a game: enter names, choose mode (Two Players / Vs Computer), name validation
- [ ] F3 Computer opponent: random legal move
- [ ] F4 New game / forfeit: "Are you sure?" pop-up, forfeit rule, history kept
- [ ] F5 Game history: list of completed games (players, mode, result)
- [ ] F6 Filter history by player name or by mode
- [ ] F7 Review moves: see the move list of a past game
- [ ] F8 Player totals: wins / draws / losses per player
- [ ] F9 Save and reopen: history + unfinished game (board, turn, names, mode, who starts next)
- [ ] Sample data file in `data/` so the instructor can test right away
### Should (makes it good)
- [ ] Theme: custom pieces/colors instead of plain X and O (theme decided by the prototype)
- [ ] Winning line highlighted on the board
- [ ] Leaderboard: totals sorted by wins
### Could (stretch, only if every Must works by Dec 7)
- [ ] Replay a past game step by step (move 1, move 2, ...)
- [ ] 4×4 board

## Build order
| When | Build | Done? |
|---|---|---|
| by Mon Nov 30 | Plan, class design, clickable HTML prototype | ☐ |
| Nov 30 – Dec 2 | Game rules in the model (F1) + tests, then a Swing board for two players | ☐ |
| Dec 2 – Dec 4 | Start screen + name rules (F2), computer opponent (F3), forfeit (F4) | ☐ |
| Dec 4 – Dec 6 | History, filters, review moves, totals (F5–F8) | ☐ |
| Dec 6 – Dec 7 | Save and reopen (F9) + sample data. **Feature freeze Dec 7** | ☐ |
| Dec 7 – Dec 9 | Bug fixes, theme polish, write-up, slides, demo practice. Test a fresh download. | ☐ |

## Risks
| Risk | What I'll do about it |
|---|---|
| Everything is new (Swing, files, big project) | One small feature at a time. Use `/explain-it` after each one so I can explain it in Q&A. |
| Save/load breaks the resume or double-counts games | Test the save → reopen round trip. Totals are calculated from history, not stored separately. |
| Running out of time / Claude usage | Must features first. Stretch goals only after Dec 7. `/clear` after each task. |
| Program doesn't run from a fresh download | Before Dec 9, download the repo into a new folder and run `run.bat`. |

## Manual test checklist
| # | Do this | Expect this | Pass? |
|---|---|---|---|
| 1 | Start Two Players with names "Ana" and "Ben", play X across the top row | "Ana wins" shows, board stops accepting clicks | ☐ |
| 2 | Fill the board with no 3 in a row | "Draw" shows | ☐ |
| 3 | Click a square that's already taken | Error message, turn doesn't change | ☐ |
| 4 | Start a game with a blank name, then with "Ana" and "ana" | Clear error each time, game doesn't start | ☐ |
| 5 | Type "Computer" as a human name | Error: that name is reserved | ☐ |
| 6 | Start Vs Computer and make moves | Computer answers each move with a legal move | ☐ |
| 7 | Play two games in a row | The other player goes first in game 2 and plays X | ☐ |
| 8 | Make 2 moves, click New Game, confirm | Player whose turn it was gets a loss marked "forfeit", history still there | ☐ |
| 9 | Click New Game with no moves made | No game added to history | ☐ |
| 10 | Open history, filter by "Ana", then by "Vs Computer" | Only matching games show | ☐ |
| 11 | Select a past game, review its moves | Moves listed in order | ☐ |
| 12 | Check totals after a few games | Wins/draws/losses match the history, each game counted once | ☐ |
| 13 | Make 3 moves, close the app, reopen | Same board, same names, same player's turn | ☐ |
| 14 | Reopen the app | All past games and totals are still there | ☐ |
| 15 | Run on a fresh download with the sample data | History and totals show right away | ☐ |
