# Retro Library (/games/): notices and notes

Static files only, nothing to build. Open `/games/` on the deployed site.

## Files (all in the site root)
- `games.html`: the whole library and player in one page, served at `/games/` (see the rewrites in `vercel.json`). It contains the game list (`GAMES`) and the thumbnails. `/games/` shows the library, `/games/?g=<id>` opens a game.
- `emulator.min.js`, `emulator.min.css`, `GameManager.js`, `gamepad.js`, `nipplejs.js`, `shaders.js`, `socket.io.min.js`, `storage.js`, `extract7z.js`, `extractzip.js`, `libunrar.js`, `libunrar.wasm`, `prboom-wasm.data`, `prboom-legacy-wasm.data`: the EmulatorJS engine and core. The engine asks for them under `/src/`, `/compression/` and `/cores/`, and `vercel.json` maps those paths to the root files.
- `freedoom1.wad`: game file.

## Games included
- **Freedoom: Phase 1** v0.13.0 (`freedoom1.wad`): BSD 3-Clause license, © 2001-2024 Contributors to the Freedoom project (as shown on the game's own title screen).
  The WAD file itself states: "Freedoom is freely redistributable under the terms of the modified BSD license."
  Project page and full license text: https://freedoom.github.io/

## Software included
- **EmulatorJS** (engine files in the root, GPL-3.0): https://github.com/EmulatorJS/EmulatorJS, copied unmodified from the portable-retro-games package.
  The page only disables the engine's update check (a call to cdn.emulatorjs.org) at run time; no engine file was edited.
- **PrBoom libretro core** (`prboom-*.data`, GPL): built by the EmulatorJS project; upstream sources are linked from emulatorjs.org.
- **portable-retro-games** (MIT, © 2026 Aciiderixx): the package these files came from. Its license is reproduced at the end of this file.

## Deliberately NOT included
The source ZIP also contains console BIOS files (PlayStation, Sega CD, Amiga Kickstart, PC-FX and others), arcade and console ROMs
and a 232 MB ScummVM bundle. The BIOS files and the commercial or unverified ROMs are copyrighted and are not redistributed here.

## Add a game (only if you have the right to host it)
1. Put the game file in the site root.
2. Copy the core for its system from the ZIP (`docs/data/cores/<core>-wasm.data` and `<core>-legacy-wasm.data`) into the site root.
3. Add an entry to `GAMES` in `games.html` (`id`, `title`, `system`, `category`, `core`, `rom`, `thumb`, `desc`, `license`, `credit`, `url`). `thumb` can be a path or a data: URL (4:3 image).
4. Test it on desktop and on a phone before deploying. Some systems (PlayStation, Sega CD, Amiga, Saturn...) also need BIOS files, which you must supply yourself.

## portable-retro-games license (MIT)

MIT License

Copyright (c) 2026 Aciiderixx

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
