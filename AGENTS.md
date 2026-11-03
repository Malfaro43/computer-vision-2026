# Agent guide: computer-vision-2026 (umbrella repo)

This root is a parent repo that only holds submodules. Do project work inside the project folder and read that folder's own guide first.

- `xgo-robot/`: XGO Lite robot dog. Read `xgo-robot/AGENTS.md` and `xgo-robot/docs/PROGRESS.md` before touching hardware. Its remote is `ChampPhil/xgo_robot_kit_playing_fetch`. The robot's checkout is still `~/project/xgo_robot_kit_playing_fetch` on the Pi.
- `drone-robot/`: new drone project (`Malfaro43/drone-robot`).

Commit inside a submodule first, then `git add <folder>` in the parent to bump its pointer. Never `git add .` inside `xgo-robot/`: `xgo_starter.py` and `AGENTS.md` are untracked on purpose.
