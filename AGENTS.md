# AGENTS.md — Crossy Road

Forward = negative Z (W/Up decreases the row; score = -row); the character faces +Z,
so a forward move faces rotation.y = PI. Camera sits behind the player, looking forward.

Collision is by mesh world position (both X and Z), never by grid row — row-only
checks kill the player from adjacent lanes.

Water is deadly unless on a log: drift with the log, don't snap the player's X back to
the grid, drown if they slide off.

Trains flash a warning, then cross fast; spawn the train rear-first (locomotive leading
inward) or it gets culled off-screen immediately.

Load the real Kenney GLBs — list each folder for exact filenames, then load/cache/clone
(box only as a per-file fallback): player = cube-pet animals from kenney_cube-pets,
cars from kenney_car-kit, trains from kenney_train-kit (re-center off-origin models).
