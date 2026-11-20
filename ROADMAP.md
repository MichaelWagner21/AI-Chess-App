# Chess Puzzle App Roadmap

Each milestone ends with a working version that can be opened in a browser and tested. Check off the items as they are completed.

## Milestone 1 - One playable puzzle

**Browser result:** Open the app and solve one puzzle sourced from a small sample row of `lichess_db_puzzle.csv`.

- [x] Show a chessboard with the puzzle position and whose turn it is.
- [x] Let the player move a piece on the board.
- [x] Accept the correct move and show a clear success state.
- [x] For an incorrect move, keep the puzzle active so the player can retry.
- [x] Verify the full flow in a browser using the bundled sample puzzle data.

## Milestone 2 - Solve a sequence

**Browser result:** Open a multi-move puzzle, enter the full solution on the board, and see the opponent's replies between the player's moves.

- [x] Read the complete move sequence for a puzzle from the CSV data.
- [x] Check each player move against the expected solution.
- [x] Automatically play the opponent's reply after each correct player move.
- [x] Allow a retry after a wrong move without advancing the sequence.
- [x] Show a completion state only after the entire line is solved.
- [x] Verify a puzzle with multiple player moves in a browser.

## Milestone 3 - Move through a small puzzle set

**Browser result:** Solve multiple puzzles one after another from a small local CSV sample.

- [x] Load more than one puzzle row from the CSV sample.
- [x] Provide a "Next puzzle" action after a puzzle is completed.
- [x] Reset the board and puzzle progress when the next puzzle loads.
- [x] Show useful feedback if puzzle data cannot be read or is malformed.
- [x] Verify that several puzzles can be completed in sequence in a browser.

## Milestone 4 - Use the full puzzle export

**Browser result:** Open the app with the full `lichess_db_puzzle.csv` export available and play puzzles selected from it.

- [ ] Decide how the browser will access the full CSV (for example, selecting the local file or preparing a smaller app data file from it).
- [ ] Handle the export's size without freezing the browser during puzzle selection.
- [ ] Choose puzzles from the loaded data and retain the same solving and retry behavior.
- [ ] Verify the full-data workflow in a browser with the actual export.

## CSV details to account for

The Lichess export is standard CSV with these columns: `PuzzleId`, `FEN`, `Moves`, `Rating`, `RatingDeviation`, `Popularity`, `NbPlays`, `Themes`, `GameUrl`, `OpeningTags`, and `DailyDate`. `Moves` contains UCI moves. The FEN is the position before the opponent's setup move: apply the first move in `Moves` to prepare the board shown to the player; the second move begins the player's solution. See the [official Lichess puzzle database format](https://database.lichess.org/#puzzles).

## Out of scope for the first version

- [ ] Puzzle difficulty selection (can be considered after the initial version).
