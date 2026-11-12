# tiny-chess-01 — a compact chess engine in 4 KB

`main.py` is the whole engine (3,993 bytes as committed): a 0x88-board
negamax search with alpha-beta pruning, quiescence over captures,
promotions and check evasions, a transposition table, MVV-LVA capture
ordering and killer moves, and a material + piece-square evaluation with
a bishop-pair bonus. It searches to a fixed node budget (150,000 nodes a
move), never to a clock, so a trial replays move for move.

It plays the house gauntlet through the env at `MAKEFUN_ENV_URL`
(`POST /game`, `POST /move`), reading each position's FEN and legal moves
from the env and choosing a move by iterative deepening.

Written from scratch by the author (not a fork of sunfish or any other
engine). MIT licensed.
