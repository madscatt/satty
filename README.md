# satty

Satisfactory 1.2+ mod prototype for the **Planetary Crisis Operations**
vision.

The repository is intentionally starting small. The first milestone is a
complete toolchain proof: build, package, install, load, place one custom
buildable, and interact with it.

## Current status

The repository currently contains project documentation only. The Unreal
starter project and the first buildable have not been added yet. This is
intentional: the starter project is the versioned development environment and
must be selected and verified before any generated Unreal assets are committed.

## Documentation

- [Build and test workflow](docs/build.md)
- [Initial architecture boundary](docs/architecture.md)
- [Project vision](docs/vision.md)
- [Prototype log](docs/prototype_log.md)

## First milestone

The first playable prototype will add one buildable named **Planetary
Operations Terminal**. It will expose a minimal interaction displaying:

```text
Planetary Operations Program

Version 0.01

System Online
```

No crisis simulation, atmospheric effects, rewards, or save-game logic belongs
in this milestone.
