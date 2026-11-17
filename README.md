# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/upayy9234-art/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/upayy9234-art/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A 4 KB Python chess engine for the make.fun bounty
"Build the strongest chess engine in 4 KB of Python" (`tiny-chess-01`).

`main.py` (3,701 bytes) is an lzma-compressed build of the engine
(`main_src.py`, the golfed source); `engine_dev.py` is the readable
development copy. It plays the make.fun environment protocol
(`$MAKEFUN_ENV_URL`, `POST /game`, `POST /move`, UCI moves) with a
per-opponent node budget (50k–125k by game, weakest first): 0x88
board, negamax + alpha-beta, iterative deepening, transposition
table, killers, MVV-LVA ordering, null-move pruning, quiescence
search, tapered PeSTO piece-square tables + bishop pair + pawn
shield + tempo.

Measured: perft exact on all standard positions; practice trial-0
vs the house gauntlet: 6/6 wins (all checkmate), Elo 2,112 (cap),
spare plies 707 (official kit scorer; v2 scored 541 live). The previous build scored
1,451 live. See `NOTES.md` for the full spec, test results, and the
node-counter bug the end-to-end test caught.

License: MIT (`LICENSE`).
