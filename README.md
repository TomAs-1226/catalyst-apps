# Catalyst apps

Apps for [Catalyst Linux](https://github.com/TomAs-1226/CatalystLinux) on the
M5Stack CardputerZero. The handheld's **Catalogue** lists them, and gets,
updates and removes them over the air.

| App | What it is | Rebuilt from |
| --- | --- | --- |
| Sudoku | One answer every time, three levels, notes and best times | sudokuzero |
| Battleship | Against a computer that hunts by probability, three levels | yutacar's Battleship |
| Typing | Speed typing with English, code and pit word lists | taM5CZTyping (key-dash) |
| Orbits | Gravity sandbox with four universes | AstroBox |
| Hello | The example to copy when writing an app | (new) |

The four games are rebuilt natively, with Catalyst Kit, from apps in
M5Stack's CardputerZero store. They follow the originals' rules and
algorithms, and each package carries its original's licence and copyright
line.

## How it works

The apps live in this repository's `catalogue` release: one signed package
per app, and `index.json` listing them.

- **Signed:** every package is signed with the catalogue's Ed25519 key. The
  handheld trusts only the public half that its system image carries.
- **Checked:** before it installs anything, the handheld checks the
  signature, the package's hash, that it is the app and version the index
  named, and that nothing in it points outside its own folder.
- **Kept safe:** apps install into `/data/apps`, never the system. What an
  app saves survives its updates.

## Writing an app

See [Catalyst Kit](https://github.com/TomAs-1226/CatalystLinux/tree/main/userland/crates/kit)
and [the catalogue's sources](https://github.com/TomAs-1226/CatalystLinux/tree/main/catalyst-apps)
in the Catalyst Linux repository. Packages are built and signed there by
`scripts/pack-catalogue.sh` and published here by
`scripts/publish-catalogue.sh`.
