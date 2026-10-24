# Community Garage

Share and download Forza Horizon 2 liveries, tunes and group vinyls from the game's own menus, with a community server.
Unofficial fan project for the PC version running on Azimuth; not affiliated with Microsoft, Turn 10 Studios or Playground Games.

Status: working. The game's Share, Find, Suggested and download screens talk to the community server. See
[docs/re-notes.md](docs/re-notes.md) for how it was worked out, and `packaging/` for the player download.

- `mod/` — FH2 Mod Platform mod (`CommunityGarage.dll`) that points the game's online
  services at a community server. Configure with `communitygarage\server.ini` next to
  `azimuth.exe`:

  ```ini
  [server]
  host=your.domain.example
  port=443
  ```
- The community server (Node.js) lives in its own repository, CommunityTunes&LiveriesServer.
- `platform/` — the FH2 Mod Platform submodule.

Build (llvm-mingw + CMake + Ninja): `cmake -S . -B build -G Ninja -DCMAKE_C_COMPILER=x86_64-w64-mingw32-clang -DCMAKE_CXX_COMPILER=x86_64-w64-mingw32-clang++ -DCMAKE_RC_COMPILER=x86_64-w64-mingw32-windres && cmake --build build`

