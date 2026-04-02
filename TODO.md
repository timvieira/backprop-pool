# TODO

- [ ] **Fullscreen mode: integrated game panel** — When entering fullscreen, the UI should feel like a video game that takes over the entire screen. All controls, results, history, and info that currently live outside the canvas should be integrated into the game panel itself (e.g., as overlays, HUD elements, or side panels drawn on/around the canvas). Nothing should feel like a webpage in fullscreen — it should feel like a self-contained game.
  - *Partially done*: Fullscreen now targets the canvas-wrap (not the whole page). HUD overlays for controls and results are in place. Still missing: history panel and verify/LR below canvas aren't visible in fullscreen.

- [ ] **Undo/redo and shot replay** — Add the ability to replay previous shots. Implement undo and redo so the user can step back through their iteration history, see the trajectory for any previous shot, and restore earlier angle/force values. The iteration history list (already showing `#1: angle=... force=... loss=...`) is the natural place to integrate this — clicking an entry could restore that shot's parameters and trajectory, effectively acting as undo. Entries after the selected one become the redo stack.

- [ ] **Shift/Ctrl + arrow keys for coarse adjustment** — Holding shift (or ctrl) while pressing arrow keys should apply a larger step size (e.g., 1° or 5° for angle, 1.0 for force) for faster manual exploration.

- [ ] **Advanced levels with obstacle-based routing** — Design levels where the ball cannot reach the hole in a straight line and must bounce off walls/obstacles. The user needs to reason about reflection angles and use the gradient to find the right bank shot. This highlights how backprop differentiates through the collision physics — a non-obvious capability. Advanced levels could introduce new physics elements: ramps, quarter pipes, ice (low friction), sand (high friction), other balls (momentum transfer), rubber walls (high restitution), etc. Each adds a new differentiable operation to the tape.

- [ ] **Sqrt loss display** — Consider showing sqrt(loss) (distance in pixels) instead of squared distance for the loss curve and contour plot, to keep units intuitive.

## Done

- [x] Backprop teaching tool (tape-based AD through physics)
- [x] Link to gradient testing blog post
- [x] README with live demo link
- [x] Friction-based stopping (no max steps)
- [x] Mobile responsive layout
- [x] Automated gradient descent (Optimize button)
- [x] Fullscreen toggle (targets game canvas)
- [x] Armijo line search (proper optimization algorithm)
- [x] Stopping criteria (gradient norm, no progress)
- [x] Style matching Graduate Descent blog (EB Garamond, muted palette)
- [x] Unified neutral color palette
- [x] HUD overlay (angle/force +/- controls, loss/dist/gradients on canvas)
- [x] Loss curve in HUD (transparent, with axis labels)
- [x] Contour plot of loss landscape (draggable, shows optimization trajectory)
- [x] Keyboard shortcuts (space, o, g, r, n, f, ?, arrows)
- [x] Tooltips with keyboard shortcuts on buttons
- [x] Help overlay (? key)
- [x] Reset button (disabled Next on last level)
- [x] Keep playing after sinking
- [x] Trajectory wall-clipping fix
- [x] Angle wraps at 360°
- [x] Real-valued parameters (0.1 step, 2 decimal places)
- [x] LR control matches +/- style (multiplicative ×10/÷10)
- [x] Previous trajectories shown on canvas
- [x] Start screen dismissable with keyboard
- [x] MAX_POWER increased to 25
