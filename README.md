# SCC – Super Cool Calculator

A Minecraft mod for **1.21.1 / NeoForge**. This repository is the **bug tracker** for it – the mod itself is published on CurseForge.

➡️ **[Report a bug or ask for a feature](../../issues/new/choose)**

## What the mod does

SCC breaks any item down into the materials it really costs – as a flat shopping list or as a full recipe tree with every intermediate step, the station it is made at and the number of crafts. Around that calculator it builds a logistics network: item, fluid, chemical and energy storage, wired and wireless terminals, autocrafting with Calculation Crafters and Processing Calculators, requesters, transfer nodes and cables.

Six star tiers – Basic, Red Dwarf, Yellow Star, Blue Giant, Neutron Star, Singularity – are forged in the Star Forge from matter a Sky Harvester pulls out of the night sky.

Recipes are read from JEI or EMI when one of them is installed, so machine recipes from other mods are understood as well. Without a recipe viewer the mod falls back to the vanilla recipe system.

## Before you report

Most questions are answered by two things:

1. **The in-game guide.** Craft the SCC Guide, or press the guide button in any SCC window.
2. **The settings (F7).** Animations, sky objects, light mode, flat blocks and every sound can be switched there.

A few answers up front:

- **The network needs power (FE) since 1.1.0.** The Calculator Controller pays from its own buffer first, then from every Energy Storage on the network. `/scc power off` turns the whole thing off.
- **With a shader pack** the star effects switch to render types a shader understands. If your pack still shows streaks, turn off "Sky objects with shaders" in F7.
- **No other mod is required.** JEI, EMI, Jade, AE2, Curios, Mekanism, Ars Nouveau and the others only add features.

## What to put in a bug report

The issue form asks for it, but in short:

- Mod version and Minecraft/NeoForge version, and the modpack if you use one.
- **`logs/scc.log`** – SCC writes its own log there: refused orders, stuck jobs, machines that hand nothing out, and frames longer than 100 ms with SCC's share of them. That file usually answers the question.
- `logs/latest.log` or the crash report if the game crashed.
- What you did, what you expected, what happened.

Screenshots of the window in question help a lot.

## Links

- CurseForge: *(link follows with the 1.1.0 release)*
- Changelog: see the CurseForge files page

## License

MIT – see [LICENSE](LICENSE).
