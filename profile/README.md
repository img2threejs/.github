<div align="center">

<img src="https://raw.githubusercontent.com/img2threejs/.github/main/brand/banner.png" alt="img2threejs — one reference image to a code-only, animation-ready Three.js model" width="100%">

**One reference image in. A code-only, animation-ready Three.js model out.**

Reconstruction *by code* — not photogrammetry, not mesh extraction, not downloaded art packs.
Every model this org produces is a TypeScript factory function you can read, diff, and animate.

[![img2threejs stars](https://img.shields.io/github/stars/img2threejs/img2threejs?style=flat&label=img2threejs&color=8b5cff)](https://github.com/img2threejs/img2threejs)
[![showcase stars](https://img.shields.io/github/stars/img2threejs/img2threejs-showcase?style=flat&label=showcase&color=38e8ff)](https://github.com/img2threejs/img2threejs-showcase)
[![License: Apache 2.0](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://github.com/img2threejs/img2threejs/blob/main/LICENSE)
[![Sponsor](https://img.shields.io/badge/Sponsor-Buy%20Me%20A%20Coffee-FFDD00.svg?logo=buymeacoffee&logoColor=black)](https://www.buymeacoffee.com/hoainhowors)

### [→ Open the live demo gallery](https://img2threejs.io/)

</div>

---

## Projects

| Project | What it is |
| --- | --- |
| **[img2threejs](https://github.com/img2threejs/img2threejs)** | The agent skill itself — a staged, quality-gated sculpting pipeline that turns one reference image into a procedural `THREE.Group` factory. Runs under Claude Code, Codex, OpenCode, or Hermes. The skill's tooling is Python 3.10+ stdlib only; the installer needs Node.js ≥ 18. |
| **[img2](https://github.com/img2threejs/img2)** | The plugin harness — installs, links, and audits plugins across agent hosts (`img2 add / list / doctor / sync`). Everything domain-specific is a plugin; the harness itself ships none. |
| **[img2threejs-showcase](https://github.com/img2threejs/img2threejs-showcase)** | The live gallery's source — every demo is generated code running in your browser. Orbit any model and read the source it was rebuilt from. Contributions welcome via PR. |
| **Gallery · [img2threejs.io](https://img2threejs.io/)** | The deployed gallery, fed by [`demos.json`](https://img2threejs.io/demos.json). |
| **Playground** | A hosted way to try img2threejs without installing anything. *Coming soon — not public yet.* |

### Plugins

Plugins are optional and add a domain on top of the base skill. This is the current
[plugin catalog](https://raw.githubusercontent.com/img2threejs/img2/main/catalog.json); install any of
them with `img2 add <id> --yes` after setting up the harness ([INSTALL.md §3](https://github.com/img2threejs/img2threejs/blob/main/docs/INSTALL.md#3-add-a-plugin-only-if-you-need-one)).

| Plugin | Adds | Access |
| --- | --- | --- |
| [character](https://github.com/img2threejs/plugin-character) | Character rigging and animation: skeleton from a GLB, skin conditioning, clip measurement, action design, and a twelve-check rig gate. | Public |
| [cs2](https://github.com/img2threejs/plugin-cs2) | Counter-Strike 2 weapon and glove skin reconstruction: intake contract, authoritative classification, finish/material recipes, and a blocking review gate. | Public |
| [img2glb](https://github.com/img2threejs/plugin-img2glb) | Turn an image into a GLB 3D mesh via the hosted TRELLIS space. | Public |
| [hello-cube](https://github.com/img2threejs/plugin-hello-cube) | Turn an image into a deterministic Three.js cube (contract exerciser) — the template to copy when [writing a plugin](https://github.com/img2threejs/img2/blob/main/docs/WRITING_A_PLUGIN.md). | Public |
| environment | Installs and manages the private img2 environment plugin. Requires authorized GitHub access. | Private |

## What makes it different

- **Code, not meshes.** Output is diffable TypeScript plus a JSON spec — no multi-megabyte binaries in your repo.
- **Animation-ready by construction.** Every model ships a runtime hierarchy: pivots, sockets, and colliders, so it can move the moment it exists.
- **Detail-first, gate-enforced.** A `detailInventory` of identity-defining details (bevels, rivets, engraved linework, wear, gloss) must map to real components before a line of Three.js is generated.
- **Token-efficient on purpose.** Deterministic Python scripts do validation, gating, spec authoring, and comparison-sheet packaging. Model tokens are spent only on visual judgment and code.
- **Honest about limits.** One image cannot reveal hidden sides. The pipeline reports per-region confidence and says so plainly instead of faking fidelity.

## Where this is going

One theme per release, so there's always a single answer to "what is this version about".
Current release: **[v2.0.0 — The Plugin Update](https://github.com/img2threejs/img2threejs/releases/tag/v2.0.0)**.
[ROADMAP.md](https://github.com/img2threejs/img2threejs/blob/main/ROADMAP.md) is the source of truth for what is shipped and what is planned.

**Shipped**

| Version | Theme |
| --- | --- |
| **v1.4** | The Weapon Update — CS2 image-matched reconstruction, projection-first finishes, family-specific adapters, structural review gates |
| **v1.5** | The Character Update — skeleton derived from the component tree and bound to `SkinnedMesh`, geodesic skinning, hair subsystem, material pipeline (v1.5.2 adds rigging and animation) |
| **v2.0** | The Plugin Update — domain registry, per-plugin blocking gates, the `img2` harness; CS2 and animated-character now ship as plugins |

**Planned**

| Version | Theme | What it unlocks |
| --- | --- | --- |
| **v2.1** | The Character Split | The in-repo `character` domain moves into `plugin-character`, so the base names no domain |
| **v2.2** | The Environment Update | Buildings, rooms, streets, vegetation, terrain-aware and multi-object reconstruction |
| **v2.3** | The Game Pipeline Update | Unity / Unreal exporters, Blender bridge, LOD + collision meshes |
| **v2.4** | The Animation Update | Auto rigging, skin weights, Mixamo compatibility, facial rig |
| **v2.5** | The AI Studio Update | Web UI, batch processing, visual prompt builder, cloud rendering |
| **v3.0** | The Procedural World Update | Multi-view reconstruction, procedural cities, semantic world understanding |

Full breakdown: [ROADMAP.md](https://github.com/img2threejs/img2threejs/blob/main/ROADMAP.md) ·
[roadmap on the site](https://img2threejs.io/#/roadmap)

## Install

You need Node.js ≥ 18, Git, Python ≥ 3.10, and one of Claude Code, Codex, OpenCode, or Hermes.

```bash
npx --yes img2threejs@latest install   # links the skill into every agent it finds
npx --yes img2threejs@latest doctor    # one line per agent: "managed" means installed
```

Restart your agent, then point it at an image:

```
/img2threejs Rebuild this object as a Three.js model, keep the proportions, angles, and colours.
```

The pipeline probes the image, writes an assessment and spec, generates the factory pass by pass, and
shows you a reference-beside-render sheet at each step until it matches.

Prefer to let your agent do it, or need plugins, updating, uninstalling, or other agents? See
[docs/INSTALL.md](https://github.com/img2threejs/img2threejs/blob/main/docs/INSTALL.md), which includes a
paste-to-agent prompt.

## Contributing

New procedural material recipes, gates, host coverage, and showcase demos are all welcome.
Start with [CONTRIBUTING.md](https://github.com/img2threejs/img2threejs/blob/main/CONTRIBUTING.md) and the
[roadmap](https://github.com/img2threejs/img2threejs/blob/main/ROADMAP.md), or open a
[**Submit a showcase demo**](https://github.com/img2threejs/img2threejs-showcase/issues/new/choose) issue to
get feedback on scope before doing the work.

## Support

img2threejs is free and open source. If it saved you time, a coffee helps keep it going:
[Buy Me a Coffee](https://www.buymeacoffee.com/hoainhowors).

## Brand

Logo, avatar, and banner assets live in [`brand/`](https://github.com/img2threejs/.github/tree/main/brand)
with usage notes.

<div align="center">
<sub>Apache-2.0 · maintained by <a href="https://github.com/hoainho">Hoài Nhớ</a></sub>
</div>
