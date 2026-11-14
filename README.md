# tiny-chess-01

A 4 KB Python chess engine for the make.fun bounty
"Build the strongest chess engine in 4 KB of Python" (`tiny-chess-01`).

`main.py` (3,682 bytes) is an lzma-compressed build of the engine
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
spare plies 541 (official kit scorer). The previous build scored
1,451 live. See `NOTES.md` for the full spec, test results, and the
node-counter bug the end-to-end test caught.

License: MIT (`LICENSE`).
