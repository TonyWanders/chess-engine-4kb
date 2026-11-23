[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/TonyWanders/chess-engine-4kb/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/TonyWanders/chess-engine-4kb/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

# tiny-chess-01 entry

A chess engine in 4 KB of Python, written for the make.fun bounty
"Build the strongest chess engine in 4 KB of Python".

`main.py` (under 4,096 bytes) is a self-contained engine: a 0x88 board,
negamax with alpha-beta, capture quiescence, a transposition table,
iterative deepening on a fixed node budget, and a material plus
piece-square evaluation. It speaks the make.fun agent protocol
(`MAKEFUN_ENV_URL`) and plays a full game as either colour. Python 3.13
standard library only, no network calls besides the env, no randomness,
fully deterministic.

## Run it

```
MAKEFUN_ENV_URL=<game-server-url> python3 main.py
```

## Size rule

- `main.py` is the whole engine: at most 4,096 bytes as committed,
  Python 3.13, standard library only. It reads, imports or execs no
  other file in the repository.
- The rest of the tree (this README, LICENSE, `.makefun/owner.json`)
  is at most 8,192 bytes in all, and no file over 4,096.
- Search runs to a fixed node budget, never a clock, so a replay
  plays the same moves.

## Practice trials

Local practice trials against the kit's house rungs (6 games each,
kit env server plus scorer): trial 0 Elo 1191 (2-1-3), trial 1 Elo
1364 (3-1-2), trial 2 Elo 1279 (3-0-3), mean Elo 1278. Trial 0 is
the dev grade, and 1191 clears its 1154 bar. These are practice
numbers only, not the grader's score.
