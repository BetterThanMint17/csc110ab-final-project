# Steering Log
<!-- How YOU directed Claude. /checkpoint drafts an entry at the end of each task and asks you to correct it.
Be honest and specific. The best entries show a moment you changed Claude's direction.
You'll use these in your write-up and slides. Template:

## <date> — <task>
- **Goal:**
- **What I asked for:**
- **How I steered / corrected Claude:** (rejected an idea, caught a bug, asked for simpler code, gave an example...)
- **What I learned:**
- **Next:**
-->

## 2026-11-25: Proposal and project plan
- **Goal:** Pick a project and write the proposal, then turn it into a project plan with rules, build order and test checklist.
- **What I asked for:** Help choosing a project. I like games, so I picked the Arcade Game (tic-tac-toe). Then I asked for a plan that covers every requirement.
- **How I steered / corrected Claude:**
  - Claude recommended one stretch goal (a smarter computer). I asked if I could have more than one, and chose replaying moves and a 4×4 board instead.
  - I didn't lock in a theme yet. I want to decide it during the prototype.
  - Claude recommended Player 1 always going first. I chose to switch who goes first every game.
  - Claude recommended throwing away unfinished games when you click New Game. I decided quitting should count as a loss, but the app has to warn the player first with an "Are you sure?" message.
  - Before saving, I asked Claude to list any unanswered questions so nothing was skipped.
- **What I learned:**
  - Tic-tac-toe is easier to save and resume than Snake.
  - A plan has to decide rules the assignment leaves open, like who goes first and what quitting means.
  - A Git tag is a snapshot of my work on the due date.
- **Next:** Pick a theme, then `/class-design` and `/ui-prototype` (due Mon Nov 30).
