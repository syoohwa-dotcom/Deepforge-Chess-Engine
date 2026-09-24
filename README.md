# Deepforge Chess Engine

Deepforge is a Windows UCI chess engine powered by the Talon 3072 NNUE Champion network. This public repository contains the ready-to-run engine package.

## Requirements

- 64-bit Windows
- A processor with AVX2 support
- A chess GUI that supports UCI engines

## Files

- `Deepforge.exe` is the chess engine.
- `lynx.nnue.champion` is the required Champion neural network.
- `LICENSE` contains the license terms.

Keep `Deepforge.exe` and `lynx.nnue.champion` in the same folder. The engine will load the network automatically when it starts.

## Install in a chess GUI

1. Download `Deepforge.exe` and `lynx.nnue.champion` into the same folder.
2. Open your chess GUI and add a new UCI engine.
3. Select `Deepforge.exe` as the engine executable.
4. Restart the GUI if it does not show the engine immediately.

This works with UCI-compatible programs such as En Croissant, Arena, Banksia GUI, Cute Chess, and ChessBase or Fritz.

## Recommended settings

```text
Threads = 6
Hash = 1024
OwnBook = true
EvalFile = lynx.nnue.champion
SearchProfile = residual_nonpv_depth=8,residual_nonpawn_max=8,smp_seed_history=1
```

Adjust `Threads` for the computer running the engine. Set `SyzygyPath` to a local tablebase folder if Syzygy tablebases are installed. Leave `PolicyFile` empty.

## Command line check

Run `Deepforge.exe`, type `uci`, and press Enter. A working installation will identify Deepforge and finish with `uciok`.

## Notes

The engine does not need Python, CUDA, a GPU, or the training tools while playing. The Champion network must remain beside the executable unless `EvalFile` is changed to another valid path.
