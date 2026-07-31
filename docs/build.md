# Build and test workflow

## Scope

This document describes the intended workflow for the first prototype. It is
not a claim that the prototype is already built; the repository is waiting for
the Satisfactory Modding Starter Project to be selected and initialized.

## Recommended development split

Use the Windows machine as the primary Unreal development and game-validation
host. Satisfactory mod development depends on the Windows-oriented Unreal
toolchain, the Satisfactory Modding Starter Project, Wwise setup, and Alpakit.
Keep this Git repository on the Mac if convenient, and synchronize it to the
Windows working copy with Git.

The M3 Mac remains useful for editing, Git, documentation, and review. A VM or
CrossOver may be explored later, but it should be treated as an experiment,
not as the baseline build environment. CrossOver is also a poor first choice
for validating a mod because it adds another compatibility layer between the
game, SML, SMM, and the packaged plugin.

## Required Windows setup

Follow the [current project setup guide](https://docs.ficsit.app/satisfactory-modding/latest/Development/BeginnersGuide/project_setup.html)
for the exact versions and setup sequence. The [starter project guide](https://docs.ficsit.app/satisfactory-modding/latest/Development/BeginnersGuide/StarterProject/ObtainStarterProject.html)
explains how to obtain the project, and the [release guide](https://docs.ficsit.app/satisfactory-modding/latest/Development/BeginnersGuide/ReleaseMod.html)
covers Alpakit packaging.

For the 1.2 toolchain, the documentation currently identifies:

- Satisfactory 1.2
- Unreal Engine 5.6.1, using the modding-community engine distribution
- Satisfactory Mod Loader (SML) 3.12-compatible starter project
- Wwise integration and generated soundbanks
- Visual Studio components required by the starter project
- Satisfactory Mod Manager (SMM) for installing SML and testing the mod

Do not commit the starter project wholesale into this repository unless the
starter-kit workflow specifically requires it. The expected arrangement is to
keep the starter project as the Unreal development workspace and keep `satty`
as the mod/plugin source inside that workspace, with only the source and
project-specific configuration tracked here.

## Milestone workflow

1. Clone or download the current 1.2 starter project on Windows.
2. Complete the starter-project setup, including Wwise and the initial C++
   build required by the toolchain.
3. Add the `satty` plugin using the starter project's documented plugin setup.
4. Create the smallest viable terminal asset by reusing an appropriate vanilla
   terminal/HUB interaction pattern.
5. Build the project and package `satty` with Alpakit.
6. Install SML and the packaged mod with SMM in a separate test profile.
7. Start Satisfactory through the modded profile and verify that the terminal:
   - appears in the build menu;
   - can be placed;
   - can be interacted with; and
   - displays the prototype status message.
8. Record the exact versions, commands, screenshots, and failures in
   `docs/prototype_log.md`.

## Packaging and installation

Alpakit is the source of truth for packaging. It produces archives under the
starter project's `Saved/ArchivedPlugins/` directory. Do not hand-copy an
unpacked Unreal plugin into the game while diagnosing the first prototype;
that makes it difficult to distinguish a packaging problem from a game-load
problem.

Install the resulting package through SMM in a dedicated test profile. Keep a
vanilla profile and a known-good save available. Do not test the first build on
an irreplaceable long-running save.

## Windows-machine access

The repository does not yet contain enough information to safely infer the
Windows machine's hostname, IP address, shared-folder settings, or SSH setup.
The simplest first arrangement is to work locally on Windows and use GitHub as
the handoff point. Network synchronization can be added after the first
successful build if it becomes useful.

## Acceptance checklist

- [ ] Starter project version recorded
- [ ] Unreal Engine version recorded
- [ ] SML/SMM versions recorded
- [ ] Wwise setup completed
- [ ] Starter project builds before satty changes
- [ ] satty plugin builds
- [ ] Alpakit package created
- [ ] SML loads with no satty-related errors
- [ ] Planetary Operations Terminal appears in the build menu
- [ ] Terminal can be placed
- [ ] Interaction displays the prototype message
- [ ] Test evidence recorded in the prototype log
