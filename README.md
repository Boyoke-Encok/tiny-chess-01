# tiny-chess-01

A chess engine in 4,096 bytes of Python for the make.fun tiny-chess-01
bounty: one game against each of eight fixed house engines, from book
openings, through the env at `$MAKEFUN_ENV_URL`.

`main.py` is the whole engine: an lzma-compressed payload with a tiny
unpacker (4,064 bytes). Unpacked it is a 0x88 negamax engine with
alpha-beta, iterative deepening to a fixed 40,000-node budget per move,
quiescence (captures, promotions, check evasions), transposition table,
killer moves, null-move pruning and late-move reductions, and a tapered
PeSTO-style piece-square evaluation. No clock, no randomness: the same
position always gives the same move, so replays match.

Run it with `MAKEFUN_ENV_URL` set; it plays all 8 games and exits.
