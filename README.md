#Vibe-coded crossy road

Prompt:

Build a Crossy Road game as a single self-contained index.html. See AGENTS.md
for the coordinate system, collision model, log riding, train spawning, and
Kenney asset pipeline — follow it exactly.

Tech: Three.js r160 via importmap (no build step, no npm). Runs with
`python3 -m http.server 8080`. Desktop + mobile.

Player: a cube-pet from the Kenney Cube Pets pack (blocky animal). 6 selectable
variants (fox/cat/panda/pig/koala/polar). Grid movement with a squash/stretch hop.

Assets: load the REAL Kenney GLB models — first list the three GLB folders
(kenney_cube-pets_1.0, kenney_car-kit, kenney_train-kit, each under
`assets/<pack>/Models/GLB format/`) to get exact filenames, then load/cache/clone them
(see AGENTS.md). Use a colored box only as a per-file fallback, not the default.

World: infinite forward-scrolling grid of lanes — grass (tree obstacles),
road (cars), water (rideable logs, drown if you miss), rail (trains with a
warning flash + horn). Difficulty scales with score. Coins on grass lanes.

Feel: isometric follow camera with smooth lerp; WebAudio SFX for hop/coin/
crash/splash; particle bursts; camera shake on death; touch swipe + on-screen
D-pad for mobile.

UI: Score / Best / Coins HUD; start screen with character select; game-over
with restart; high score in localStorage.

Acceptance criteria:
- WASD/arrows move the cube-pet on the grid with a hop.
- Cars kill only on real overlap (position-based collision, per AGENTS.md).
- Logs are rideable; falling in the water drowns you.
- Trains warn, then cross fast; real Kenney GLB pets, cars, and trains render (boxes only if a file fails).
- Runs via python3 -m http.server, single index.html, no build step.

Build the complete game now.
