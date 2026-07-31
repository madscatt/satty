# Initial architecture boundary

## Prototype only

The first implementation should have only three responsibilities:

1. Register the `satty` plugin with SML.
2. Register one buildable, Planetary Operations Terminal, in the build menu.
3. Provide one interaction that opens a minimal status message or widget.

The implementation should prefer existing Satisfactory classes, assets, and
interaction patterns. A temporary visual and a placeholder interaction are
acceptable if they prove the complete workflow.

## Explicitly out of scope

- crisis definitions or progression;
- atmospheric, world, or lighting effects;
- rewards, currencies, or unlock trees;
- save-game persistence;
- multiplayer-specific behavior;
- custom art pipeline beyond what is needed to identify the terminal;
- public release packaging or mod-repository publication.

## Decision points to record

Before adding complexity, record the choice in `prototype_log.md`:

- Blueprint-only versus C++ support for the terminal;
- reused vanilla mesh versus temporary custom mesh;
- message, vanilla interaction, or widget implementation;
- whether the build menu entry is always available or gated by an existing
  vanilla unlock.

The prototype is successful when it proves the toolchain, not when it settles
the long-term game architecture.
