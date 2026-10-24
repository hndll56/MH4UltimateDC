# MH4U PC direction

This fork aims to make MH4U comfortable on a single PC display, with controls and HUD flow inspired by MHGU. It keeps MH4U's game data and mechanics. The existing `native/` branch is the runtime foundation; this document adds the player-facing acceptance criteria.

## Release gates

1. **Playable baseline:** boot, create or load a character, visit the village, accept a quest, complete a hunt, return, save, and load again. Record crashes and frame times on the reference PC.
2. **One-screen play:** every required touch action has a keyboard and controller path. The map, target camera, item shortcuts, chat, and contextual prompts work without showing a second-screen window. Keep an optional touch view for debugging and accessibility.
3. **PC controls:** remappable keyboard and controller bindings, mouse camera, readable prompts, and no stuck input when opening or closing the app menu.
4. **Stable display:** 16:9 and ultrawide layouts keep gameplay and menu elements visible. Test 60 fps before raising the cap; measure frame time and gameplay speed separately.
5. **Native runtime:** replace Azahar dependencies in the order tracked by `ROADMAP.md` and `STATUS.md`. Do not remove a dependency until its replacement passes the same game-state, audio, graphics, and save checks.

## Version and asset gate

The current recompiler, function table, and hooks target the USA update whose title version is 1072. The game may display `Ver. 1.1`; that label alone does not identify the executable. Verify update title ID and code hash before running address-based hooks. Never bypass the version check to make an unknown binary boot. Game files, generated code, captures, and keys stay outside Git.

Work that does not require game files may proceed with synthetic tests. Gameplay and performance gates require a compatible decrypted dump supplied locally by a tester who owns the game.
