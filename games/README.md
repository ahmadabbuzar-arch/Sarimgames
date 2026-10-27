# /games/ (Retro Library)

Static files only; nothing to build. Open `/games/` on the deployed site.

- `index.html`: library (search, category filter, cards). Loads only `games.json` and thumbnails.
- `play.html?g=<id>`: player. Loads `emu/` and the game file only when a game page is opened (and the game data after you press START).
- `games.json`: the list of games. A game appears in the library only if it has an entry here.
- `emu/`: EmulatorJS engine and the cores that are actually used.
- `roms/`, `thumbs/`: game files and thumbnails.

## Add a game (only if you have the right to host it)
1. Put the file in `roms/` and a 4:3 image in `thumbs/`.
2. Copy the core for its system from the ZIP (`docs/data/cores/<core>-wasm.data` and `<core>-legacy-wasm.data`) into `emu/cores/`.
3. Add an entry to `games.json` (`id`, `title`, `system`, `category`, `core`, `rom`, `thumb`, `desc`, `license`, `credit`, `url`).
4. Test it on desktop and on a phone before deploying. Some systems (PlayStation, Sega CD, Amiga, Saturn...) also need BIOS files, which you must supply yourself.
