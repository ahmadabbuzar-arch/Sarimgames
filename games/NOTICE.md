# Notices for /games/

## Games included
- **Freedoom: Phase 1** v0.13.0 (`roms/freedoom1.wad`): BSD 3-Clause license, © 2001-2024 Contributors to the Freedoom project (as shown on the game's own title screen).
  The WAD file itself states: "Freedoom is freely redistributable under the terms of the modified BSD license."
  Project page and full license text: https://freedoom.github.io/

## Software included
- **EmulatorJS** (`emu/`, GPL-3.0): https://github.com/EmulatorJS/EmulatorJS, copied unmodified from the portable-retro-games package.
  The page only disables the engine's update check (a call to cdn.emulatorjs.org) at run time; no engine file was edited.
- **PrBoom libretro core** (`emu/cores/prboom-*.data`, GPL): built by the EmulatorJS project; upstream sources are linked from emulatorjs.org.
- **portable-retro-games** (MIT, © 2026 Aciiderixx): the package these files came from. License copy: `LICENSE-portable-retro-games.txt`.

## Deliberately NOT included
The source ZIP also contains console BIOS files (PlayStation, Sega CD, Amiga Kickstart, PC-FX and others), arcade and console ROMs
and a 232 MB ScummVM bundle. The BIOS files and the commercial or unverified ROMs are copyrighted and are not redistributed here.
