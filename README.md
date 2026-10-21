# Nova 4:3 Aspect Ratio Collection

**[Open the launchpad](https://jevonlipsey.github.io/nova-43aspect/)**

A curated index of native 4:3 aspect ratio, UI containment and compatibility mods for games that ship locked to 16:9. They are built for 4:3 displays: the Retroid Pocket Nova (1280x960), CRT setups, and custom resolutions.

Each mod lives in its own repository with its own browser patcher on GitHub Pages. This repo holds no mod code. It is the landing page and master index for the set.

Every patcher works on your own legally owned copy of the game. Files are patched locally in the browser and never uploaded, and no game files are distributed by any of these projects.

## Game compatibility matrix

| Game | Status | Mod Method | Web Patcher | Source Repo |
| :--- | :--- | :--- | :--- | :--- |
| **Spelunky 2** | Complete | Proxy DLL (`discord_game_sdk.dll`) + Heap Patch | [Web Patcher](https://jevonlipsey.github.io/spelunky2-43aspect/) | [Repo](https://github.com/jevonlipsey/spelunky2-43aspect) |
| **Chef RPG** | Complete | Managed Assembly (`Assembly-CSharp.dll`) | [Web Patcher](https://jevonlipsey.github.io/chefrpg-43aspect/) | [Repo](https://github.com/jevonlipsey/chefrpg-43aspect) |
| **Celeste** | Complete | Standalone EXE Patch / Everest Mod | [Web Patcher](https://jevonlipsey.github.io/celeste-43aspect/) | [Repo](https://github.com/jevonlipsey/celeste-43aspect) |
| **Enter the Gungeon** | In Progress | IL / Camera Hooks | Coming Soon | [Repo](https://github.com/jevonlipsey/gungeon-43aspect) |
| **Hades II** | Planned | Targeted Boon-Selection UI Scale | TBD | TBD |
| **Absolum** | Planned | Native Aspect Mod | TBD | TBD |

What each patcher takes:

| Game | File you patch | Notes |
| :--- | :--- | :--- |
| Spelunky 2 | `Spel2.exe` | The web patcher embeds the 4:3 mod and the Android heap fix in the exe. On PC you can instead drop in `discord_game_sdk.dll` from the [latest release](https://github.com/jevonlipsey/spelunky2-43aspect/releases/latest). Use one, not both. |
| Chef RPG | `Chef RPG_Data/Managed/Assembly-CSharp.dll` | Desktop patchers for Windows, macOS and Linux are on the [releases page](https://github.com/jevonlipsey/chefrpg-43aspect/releases). |
| Celeste | `Celeste.exe` | Needs the FNA 1.4.0.0 build (Steam: Properties → Betas → `beta 1.3.3.0`). The web patcher refuses an exe that already has Everest; use the [CelesteFit](https://github.com/jevonlipsey/celeste-43aspect/releases/latest) Everest mod for that. |

## Quick guide

### Android (DroidDeck / GameNative)

These apps run the Windows build of the game through Proton or Wine, so you patch the Windows files.

1. **Open the game's web patcher on the handheld itself.** The [launchpad](https://jevonlipsey.github.io/nova-43aspect/) links to each one.
2. **Pick the file from the game folder** (see the table above) and save the patched copy. Keep the original as a `.bak`.
   - DroidDeck: games live in its Linux environment at `/root/.local/share/Steam/steamapps/common/<Game>/`. Use desktop mode's file manager, or copy the file out to Android storage and back.
   - GameNative: containers sit in the app's private data directory. Whether your build exposes them to a file manager varies by version.
3. **Replace the original** with the patched file.
4. **Give the game a 4:3 surface.** In DroidDeck's display settings, set:
   - **Resolution:** `Match screen (1280x960)`
   - **16:9 game fit:** `Stretch` (off). `Keep proportions` letterboxes the game back into a 16:9 box.

   For GameNative, set the container resolution to the panel's native size, with no 16:9 letterboxing.
5. **Fully exit and relaunch** both the app and the game. Display changes apply on the next session.

If black bars remain after patching, the cause is almost always the container's resolution rather than the mod.

For Celeste on Android, use the web patcher rather than Everest. Getting Everest to boot under Proton on ARM64 needs extra work, covered in [celeste-everest-proton-arm64](https://github.com/jevonlipsey/celeste-everest-proton-arm64).

### Native PC (Windows / macOS / Linux)

1. Open the game's web patcher and patch the file from your game folder, or download the prebuilt files from the Releases page of the game's repo.
2. Replace the originals in your game folder. Keep backups.
3. Set the game to your display's native 4:3 resolution (for example 1280x960, 1024x768 or 1600x1200).

On both platforms, Steam's "Verify integrity of game files" and game updates restore the original files. Re-patch after either. To uninstall, restore your backup.

Each mod's own README has the full install steps, configuration and troubleshooting.

## Repository layout

| Path | Purpose |
| :--- | :--- |
| `README.md` | this index |
| `docs/index.html` | the static launchpad, served by GitHub Pages (Settings → Pages → deploy from `main`, `/docs`) |
| `docs/img/` | card thumbnails, Steam store screenshots cropped to 800x600 |

To add a game, add a row to the matrix above, a card to `docs/index.html` and a thumbnail to `docs/img/`.

## Credits

- [GabrielGabriel197](https://github.com/GabrielGabriel197/Spelunky2-Android-Patch) for the original Spelunky 2 Android patch.
- [mikumaker/Celeste-Fit](https://github.com/mikumaker/Celeste-Fit), whose 4:3 work CelesteFit ports.
- Mono.Cecil, Everest, MonoMod and FNA.

Not affiliated with or endorsed by any of the games' developers or publishers. All games, their files and screenshots belong to their respective owners.
