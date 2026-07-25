<div align="center">

<img src="https://raw.githubusercontent.com/img2threejs/.github/main/brand/banner.png" alt="img2threejs — one reference image to a code-only, animation-ready Three.js model" width="100%">

**One reference image in. A code-only, animation-ready Three.js model out.**

Reconstruction *by code* — not photogrammetry, not mesh extraction, not downloaded art packs.
Every model this org produces is a TypeScript factory function you can read, diff, and animate.

[![img2threejs stars](https://img.shields.io/github/stars/hoainho/img2threejs?style=flat&label=img2threejs&color=8b5cff)](https://github.com/hoainho/img2threejs)
[![showcase stars](https://img.shields.io/github/stars/hoainho/img2threejs-showcase?style=flat&label=showcase&color=38e8ff)](https://github.com/hoainho/img2threejs-showcase)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://github.com/hoainho/img2threejs/blob/main/LICENSE)

### [→ Open the live demo gallery](https://hoainho.github.io/img2threejs-showcase/)

</div>

---

## Projects

| Project | What it is |
| --- | --- |
| **[img2threejs](https://github.com/hoainho/img2threejs)** | The agent skill itself — a staged, quality-gated sculpting pipeline that turns one reference image into a procedural `THREE.Group` factory. Runs under Claude Code, Codex, or OpenCode. Python 3.10+ stdlib only, zero dependencies. |
| **[img2threejs-showcase](https://github.com/hoainho/img2threejs-showcase)** | The live gallery — every demo is generated code running in your browser. Orbit any model and read the source it was rebuilt from. Contributions welcome via PR. |

## What makes it different

- **Code, not meshes.** Output is diffable TypeScript plus a JSON spec — no multi-megabyte binaries in your repo.
- **Animation-ready by construction.** Every model ships a runtime hierarchy: pivots, sockets, and colliders, so it can move the moment it exists.
- **Detail-first, gate-enforced.** A `detailInventory` of identity-defining details (bevels, rivets, engraved linework, wear, gloss) must map to real components before a line of Three.js is generated.
- **Token-efficient on purpose.** Deterministic Python scripts do validation, gating, spec authoring, and comparison-sheet packaging. Model tokens are spent only on visual judgment and code.
- **Honest about limits.** One image cannot reveal hidden sides. The pipeline reports per-region confidence and says so plainly instead of faking fidelity.

## Where this is going

One theme per release, so there's always a single answer to "what is this version about".

| Version | Theme | What it unlocks |
| --- | --- | --- |
| **v1.4** | 🔫 The Weapon Update · *shipping soon* | 1:1 photorealistic hard-surface assets — strict PBR + texture projection, mechanical reasoning, metal/polymer/wood |
| **v1.5** | 👤 The Character Update · *in progress* | Character reconstruction, facial features, rigging-ready topology, blendshape prep |
| **v1.6** | 🌍 The Environment Update | Buildings, rooms, streets, vegetation, terrain-aware and multi-object reconstruction |
| **v1.7** | 🎮 The Game Pipeline Update | Unity / Unreal exporters, Blender bridge, LOD + collision meshes |
| **v1.8** | 🎬 The Animation Update | Auto rigging, skin weights, Mixamo compatibility, facial rig |
| **v1.9** | 🤖 The AI Studio Update | Web UI, batch processing, visual prompt builder, cloud rendering |
| **v2.0** | 🚀 The Procedural World Update | Multi-view reconstruction, procedural cities, semantic world understanding, plugin API |

**The arc:** assets (v1.4–v1.5) → worlds (v1.6–v1.7) → production, rigging and engine exporters
(v1.8–v1.9) → an AI game-asset platform that generates playable worlds from reference images (v2.0).

Full breakdown: [ROADMAP.md](https://github.com/hoainho/img2threejs/blob/main/ROADMAP.md) ·
[roadmap on the site](https://img2threejs-showcase.pages.dev/#/roadmap)

## Try it in two commands

```bash
git clone https://github.com/hoainho/img2threejs.git ~/.claude/skills/img2threejs
```

Then, in your agent, point at an image:

```
/img2threejs Rebuild this object as a Three.js model, keep the proportions, angles, and colours.
```

The pipeline probes the image, writes an assessment and spec, generates the factory pass by pass, and
shows you a reference-beside-render sheet at each step until it matches.

## Contributing

New procedural material recipes, gates, host coverage, and showcase demos are all welcome.
Start with [CONTRIBUTING.md](https://github.com/hoainho/img2threejs/blob/main/CONTRIBUTING.md) and the
[roadmap](https://github.com/hoainho/img2threejs/blob/main/ROADMAP.md), or open a
[**Submit a showcase demo**](https://github.com/hoainho/img2threejs-showcase/issues/new/choose) issue to
get feedback on scope before doing the work.

## Brand

Logo, avatar, and banner assets live in [`brand/`](https://github.com/img2threejs/.github/tree/main/brand)
with usage notes.

<div align="center">
<sub>Apache-2.0 · maintained by <a href="https://github.com/hoainho">Hoài Nhớ</a></sub>
</div>
