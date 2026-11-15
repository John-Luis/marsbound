# MarsBound audio assets

These supplied assets are loaded by the Web Audio runtime after the player enables sound.

- `The_Crimson_Reach.mp4` plays once when the landing intro begins at a dedicated higher level; the continuous music bed is ducked beneath it.
- `mars_walk.wav` and `mars_rover_move.wav` play for on-foot and rover movement.
- `drill_sfx.wav`, `handheld_rock_scan.wav`, and `rock_analyzer.wav` play for field science.
- `mars_rover_enter.wav`, `mars_rover_charge.wav`, and `rover_low_battery.wav` play for rover state changes.
- `oxygen_tank_fill.wav`, `eating_ration.wav`, `hungry_stomach.wav`, and `low_oxygen_hypoxia.wav` cover life support.
- `sandstorm.wav`, `solar_flare_radiation.wav`, and `mars_chilly_night.wav` cover hazards.
- Region ambience uses the canyon, ravine, dune, and cave files.
- Rex uses the bark, idle, run, and noise files for companion feedback.

## Background mix and controls
`Last_Breath_of_a_Planet.mp4` is the continuous music bed (provided locally by the user). It streams and loops without decoding the entire video into memory. Base levels: 11% in the starting menu and outdoors, 8% inside, 5.5% during hazards, 7% in paused screens, multiplied by master volume (default 50%). Audio starts after a user gesture; a saved mute preference is respected. Hidden tabs pause all media. Music resumes at its previous position.

Environment recordings crossfade over approximately two seconds; they are not restarted every three seconds. One instance per sound file and at most eight recorded effects may play concurrently. Failed files are suppressed for the current session. Intro media shares master mute/volume. Narration remains disabled. Master volume and mute are stored under `marsbound.audio.v1`.

Track attribution/licensing: supplied by the user; add creator and license details before distribution.

## Action duration fixes
Original recordings remain intact. Playback windows trim drilling to 0.6s (the drill animation), individual footsteps to 0.28s, scanning to 0.8s, rover entry to 0.7s, and most alerts/interactions to 0.45–1.2s with short fade envelopes. Drilling now follows the astronaut's drilling state, not inventory changes (including Rex pickups). Loading audio is cancelled if its action has already ended. The rover uses one movement/idle loop; movement-state changes stop the previous loop immediately and dismounting stops both. Background music is unaffected.

## Supplied action recordings (November 15)
Optimized Ogg Vorbis copies use the user's originals from drive-download-20261115T134155Z-1-001. Originals in Downloads are untouched. Kept 44.1kHz mono, encoded at Vorbis quality 4, trimmed to action length with 10ms attack/60ms release. The two rocket WAVs have identical SHA-256 hashes; only one optimized asset is included.

- airlock_cycle.ogg: sealing Command's bulkhead, 1.2s.
- building_enter_exit.ogg: crossing a shelter boundary, 0.8s.
- crafting_fabricate.ogg: successful upgrade fabrication, including menu purchases, 1.2s.
- habitat_walking.ogg: indoor footsteps, 0.28s per step.
- inventory_full_error.ogg: inventory-full and supported unavailable-action messages, 0.45s.
- mars_rocket_takeoff.ogg: successful/partial return cinematics, 3s; cancelled on leaving the scene.
- research_scan_complete.ogg: lab research and hazard-task completion, 1s maximum.
- sleeping_cycle.ogg: sleep/wake transition cue, 1s (not a continuous breathing loop).
- weather_beacon_deploy.ogg: beacon placement, 1.2s.
- The_Last_Measure_of_Light.m4a: ending-screen music, audio-only AAC 128kbps. Main music remains quietly underneath and continues during gameplay.

Nine effects total about 96KB versus 3.4MB of unique source WAV files. Ending music is about 2.86MB instead of an 8.31MB video. Source creator/license attribution remains user-supplied.
