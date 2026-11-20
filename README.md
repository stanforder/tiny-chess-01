# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/stanforder/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/stanforder/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A strong chess engine in 4 KB of Python, built for the
[make.fun tiny-chess-01 bounty](https://make.fun/bounty/tiny-chess-01):
the strongest engine that fits in 4,096 bytes of `main.py`.

## Engine

`main.py` is the whole engine (Python 3.13, standard library only). It
speaks the bounty environment protocol over HTTP (`MAKEFUN_ENV_URL`) and
plays with a fixed node budget, so every game is fully deterministic.

- 0x88 board, make/unmake with Zobrist hashing and a transposition table
- negamax alpha-beta with iterative deepening at a fixed 90,000 nodes/move
- null-move pruning, late-move reductions, check extensions, quiescence
- tapered piece-square tables, pawn structure, rook files, king safety

The readable source is `engine.py`; `main.py` is the same program packed
with the competition kit's LZMA compressor (`minify.py` shrinks it first).

## Test locally

Practice trials run against the kit's environment server without Docker;
see `run_trial.sh` and `quick_test.sh` in the kit checkout.

## License

MIT — see `LICENSE`.
