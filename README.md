# SimpleModules

Add-on modules for the [RobotsMadeSimple](https://github.com/RobotsMadeSimple) robot ecosystem.

Each top-level directory is a self-contained **module** — a physical accessory that extends the robot (conveyors, feeders, fixtures, etc.). A module holds its print files (and, where relevant, docs and a BOM) so it can be built on its own.

## Modules

| Module | Description |
|--------|-------------|
| [`SimpleConveyor`](SimpleConveyor) | Belt conveyor: bearing brackets, motor bracket, belt roller, and modular conveyor surface. |

## Repository layout

```
<ModuleName>/
  Print Files/        # STL / CAD files to print or machine
```

## Git LFS

3D geometry (`.stl`, `.step`/`.stp`, `.3mf`, `.f3d`/`.f3z`, `.obj`) is stored in **[Git LFS](https://git-lfs.com/)**. Install it once before cloning so you get the real files instead of pointer stubs:

```bash
git lfs install
git clone https://github.com/RobotsMadeSimple/SimpleModules.git
```

If you cloned before installing LFS, run `git lfs pull` to fetch the binaries.

## Print-file releases

Every module's print files are published as a downloadable ZIP under [Releases](https://github.com/RobotsMadeSimple/SimpleModules/releases), so you can grab a module's files without cloning the repo or installing LFS.

Packaging is automated: on every push to `main`, a GitHub Action detects which module directories changed and rebuilds **only those** releases. Each module has one rolling release tagged with the module name (e.g. `SimpleConveyor`), whose ZIP asset is overwritten with the latest print files.

## Adding a module

1. Create a new top-level directory named after the module.
2. Put its print files under `<ModuleName>/Print Files/`.
3. Commit and push to `main` — the Action creates/updates the module's release automatically.
