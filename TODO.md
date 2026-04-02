# TODO

- [ ] **Fullscreen mode: integrated game panel** — When entering fullscreen, the UI should feel like a video game that takes over the entire screen. All controls, results, history, and info that currently live outside the canvas should be integrated into the game panel itself (e.g., as overlays, HUD elements, or side panels drawn on/around the canvas). Nothing should feel like a webpage in fullscreen — it should feel like a self-contained game.

- [ ] **Undo/redo and shot replay** — Add the ability to replay previous shots. Implement undo and redo so the user can step back through their iteration history, see the trajectory for any previous shot, and restore earlier angle/force values. The iteration history list (already showing `#1: angle=... force=... loss=...`) is the natural place to integrate this — clicking an entry could restore that shot's parameters and trajectory, effectively acting as undo. Entries after the selected one become the redo stack.

- [ ] **Shift/Ctrl + arrow keys for coarse adjustment** — Holding shift (or ctrl) while pressing arrow keys should apply a larger step size (e.g., 1° or 5° for angle, 1.0 for force) for faster manual exploration.

- [ ] **Sqrt loss display** — Consider showing sqrt(loss) (distance in pixels) instead of squared distance for the loss curve and contour plot, to keep units intuitive.
