# computer-vision-2026

Umbrella repository for the 2026 computer-vision robotics projects. Each project is its own Git repository, linked here as a submodule.

| Folder | Repository | Project |
| --- | --- | --- |
| [`xgo-robot/`](xgo-robot) | [ChampPhil/xgo_robot_kit_playing_fetch](https://github.com/ChampPhil/xgo_robot_kit_playing_fetch) | XGO Lite robot dog: color-block detection, teleop, fetch/pickup |
| [`drone-robot/`](drone-robot) | [Malfaro43/drone-robot](https://github.com/Malfaro43/drone-robot) | RoboMaster TT drone: searches for a target pad and maps a safe route, which the XGO dog then walks (laptop bridge for both robots) |

The two projects work together: `drone-robot` drives both robots from the laptop through its `tello_xgo_bridge`, and the dog's side of that link (`POST /command` with a stop-if-silent watchdog) lives in `xgo-robot/scripts/xgo_robot/`. Start with [`drone-robot/README.md`](drone-robot/README.md); try it all in simulation with `drone-robot/scripts/run_mission.py --sim`.

## Clone

```bash
git clone --recurse-submodules https://github.com/Malfaro43/computer-vision-2026.git
# already cloned without submodules:
git submodule update --init --recursive
```

## Working with submodules

Commit and push inside the project folder first, then record the new pointer in the parent:

```bash
cd xgo-robot && git commit -am "..." && git push && cd ..
git add xgo-robot && git commit -m "Bump xgo-robot" && git push
```

Pull the latest of every project: `git submodule update --remote --merge`.
