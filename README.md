# tiny-chess-01

A 4 KB Python chess engine for the make.fun bounty
"Build the strongest chess engine in 4 KB of Python" (`tiny-chess-01`).

`main.py` (4,090 bytes) is an lzma-compressed build of the engine
(`main_src.py`, the golfed source); `engine_dev.py` is the readable
development copy. It plays the make.fun environment protocol
(`$MAKEFUN_ENV_URL`, `POST /game`, `POST /move`, UCI moves) with a
fixed 100,000-node budget per move: 0x88 board, negamax + alpha-beta,
iterative deepening, transposition table, killers, MVV-LVA ordering,
null-move pruning, quiescence search, material + piece-square tables
with a tapered king.

Measured: perft exact on all standard positions; practice Elo ~1,321
over two 6-game practice trials vs the house gauntlet (trial-0: 4/6 =
1,451; trial-2: 2.5/6 = 1,191). See `NOTES.md` for the full spec,
test results, and the node-counter bug the end-to-end test caught.

License: MIT (`LICENSE`).
