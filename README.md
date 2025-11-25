# Spritz-Wine-TkG (AUR)

`Spritz-Wine-TkG` is a custom Wine build aimed at making playing certain
anime games easier, without missing any of Wine's latest additions.

These builds are different from the [AAGL builds](https://github.com/NelloKudo/Wine-Builds/releases): they have many more experimental patches.

## Download

- [AUR](https://aur.archlinux.org/packages/spritz-wine-bin)
- [Releases](https://github.com/NelloKudo/Wine-Builds/releases)

## Features:

- Rebased to **latest wine-staging**
- Backported/reworked many patches from Proton, mostly aiming controllers
- Includes many of Wine-TkG's fixes
- Includes backports from [Proton-EM](https://github.com/Etaash-mathamsetty/Proton)
- Fixes various issues with **certain anime games**
- Includes some QoL fixes for dropping inputs, random crashes and alt-tabbing.

## Useful environmental variables

- Spritz patches:
  - `PROTON_DISABLE_AEDEBUG=1`: disables AeDebug, fixes issues with some games
  - `WINE_DISABLE_DISCONNECT=1`: disables the disconnecting trick when enabled by default
  - `WINE_ENABLE_DISCONNECT=1`: enables the disconnecting trick
  - `WINE_ENABLE_STEAM_STUB=1`: launches the executable using the `steam.exe` stub in the builds

- Proton imported patches:
  - `PROTON_PREFER_SDL=1`: uses SDL instead of hidraw, disabling it (already default)
  - `PROTON_DISABLE_HIDRAW=1`: disables hidraw (already default)
  - `PROTON_ENABLE_HIDRAW=1`: enables hidraw, fixes PlayStation glyphs not showing in some games

## Builds description

Spritz builds are built in a Docker container based on Proton's SDK, with a few changes you can see in the Dockerfile. The `wine-builder` container is hosted [here](https://hub.docker.com/r/nellokudo/wine-builder), built from its apposite [GitHub CI](https://github.com/NelloKudo/WineBuilder/actions/workflows/dockerhub.yml) from my main repository of [WineBuilder](https://github.com/NelloKudo/WineBuilder).

Many thanks to spectator's work in the main repository for the polished building process.
