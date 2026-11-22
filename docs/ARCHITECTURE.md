<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-PHYSICAL — repository foundation
-->

# Repository architecture

## Current executable tooling

**What it contains:** the repository's metadata, source-provenance, workflow, dependency-alignment, documentation, inventory and preflight controls.

**What each control does:** it inspects its fixed, declared local scope.

**What received metadata cannot do:** select another acceptance policy or grant domain authority.

Foundation qualification is in progress.

## Intended domain boundaries

| Record | Responsibility | Required evidence |
| --- | --- | --- |
| Physical operation | Floorplan, macro/pad placement, power-grid, clock-tree, routing, dummy-fill exclusion and sign-off extraction constraints, consuming analogue-derived clock-jitter uncertainty | Pinned synthesis netlist, leaf-cell map, DFT scan manifest and technology-profile digests |
| Physical result | `GDSII`/`OASIS` stream digests, `FST` gate-level timing simulation support, post-dummy-fill parasitic extraction and multi-corner `OpenSTA` timing, IR-drop/electromigration margins, `Magic`-versus-`KLayout` dual-DRC, `Netgen` LVS, `HBM`/`CDM` ESD and power-on-control latch-up checks, backside-substrate net binding, focused-ion-beam/backside-IR fiducials and dual-approved foundry DRC waivers | Zero unwaived DRC/LVS/antenna/hold/ESD errors after dummy fill, with macro power-pin and hold margins verified |
| Shuttle top harness specification | Multi-project-wafer wrapper (`Caravel` or foundry frame) pinout, power-pad ring, `OpenRAM`/macro hookup, `GDSII` cell-prefix collision check and scribe/seal-ring rules | Verified wrapper hold margins, power-pin connectivity and unique cell-name prefixes across merged IP |

## Licence isolation

- **Separate-process EDA binaries.** `OpenROAD` (`BSD-3-Clause` with copyleft sub-components), `OpenSTA` (`GPL-3.0`), `KLayout` (`GPL-3.0`), `Netgen` (`GPL-1.0+`) and proprietary foundry sign-off tools execute strictly as separate processes over file boundaries; permissive `Magic` (`MIT`-style) scripts respect the same pinned container digests.

## Planned record schemas

- `circuit_physical.physical_operation.v1`
- `circuit_physical.physical_result.v1`
- `circuit_physical.shuttle_top_harness_spec.v1`

These are planned identifiers. None of them is registered or qualified here.

Read [validation tooling](validation-tooling.md) for the executable repository interfaces.
