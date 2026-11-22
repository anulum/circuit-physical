<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-PHYSICAL — repository foundation
-->

# Circuit Physical

Circuit Physical is being built to run deterministic physical implementation from synthesised netlists to tapeout-ready `GDSII` or `OASIS` layouts — enforcing post-dummy-fill parasitic extraction and static timing, dual-tool design-rule checking, layout-versus-schematic equivalence, electrostatic-discharge and latch-up tie-offs, backside-substrate binding, failure-analysis fiducials and multi-project-wafer shuttle harness integration — completely without requiring AI. This checkout contains repository validation tooling and documentation only. Full foundation qualification is in progress. There is no installed place-and-route runner, static-timing engine, dual-DRC/LVS checker, shuttle harness builder or qualified record schema.

**What does not exist yet:**
- a floorplanning, place-and-route, parasitic-extraction, timing or DRC/LVS runner;
- a registered runtime record schema;
- any migrated ASIC-flow module or tapeout layout.

## Boundary

**What this project owns:**

| Record | Scope |
|---|---|
| Physical operation | Floorplan, macro/pad placement, power-grid, clock-tree, routing, dummy-fill exclusion and sign-off extraction constraints, consuming analogue-derived clock-jitter uncertainty |
| Physical result | `GDSII`/`OASIS` stream digests, `FST` gate-level timing simulation support, post-dummy-fill parasitic extraction and multi-corner `OpenSTA` timing, IR-drop/electromigration margins, `Magic`-versus-`KLayout` dual-DRC, `Netgen` LVS, `HBM`/`CDM` ESD and power-on-control latch-up checks, backside-substrate net binding, focused-ion-beam/backside-IR fiducials and dual-approved foundry DRC waivers |
| Shuttle top harness specification | Multi-project-wafer wrapper (`Caravel` or foundry frame) pinout, power-pad ring, `OpenRAM`/macro hookup, `GDSII` cell-prefix collision check and scribe/seal-ring rules |

**Static imports:** only Circuit Core and Circuit Technology.

**Records read without importing domain code:**

| Source | Records consumed |
|---|---|
| Circuit Core and Circuit Technology | design views, budgets, compartments, operation profiles, approvals, autonomy envelopes, technology profiles and leaf-cell maps |
| Circuit Digital, Circuit Analog, Circuit Mixed-Signal, Circuit Fields and Circuit Photonics | synthesised netlists, scan/DFT manifests, firmware ROM images, derived clock-jitter bounds, coupled results, thermal/EM maps and photonic layouts |
| Circuit Assembly | assembly views and chiplet/3D micro-bump stacks |
| Circuit Acceptance, Circuit Flow, Circuit Learning and Circuit Manufacturing | qualification/acceptance records, learning records, graph/grader specs and corrective-action metal-fix records |
| Evidence Manifest Toolkit | shared evidence manifest envelopes |

**Capability registration and handoffs:** Registers the physical tool-profile manifest with Circuit Core, delivers layout and shuttle packages to Circuit Assembly, Circuit Manufacturing and Circuit Acceptance, and receives the generic ASIC flow split from SC-NeuroCore.

**Explicit non-claims and operating boundaries:**
- Every physical implementation and sign-off step works deterministically without machine learning.
- Pre-dummy-fill timing or DRC never qualifies tapeout: parasitic extraction and static timing must run after metal dummy-fill insertion (respecting analogue/RF/photonic exclusion zones).
- Foundry design-rule waivers never pass silently: every waiver requires an explicit dual person-in-role approval record.
- `OpenROAD`, `OpenSTA`, `KLayout` and `Netgen` (`GPL-1.0+`) execute strictly as separate processes over file boundaries.

## Current tooling

Repository controls inspect:
- metadata and source attribution;
- workflows and dependency alignment;
- native documentation and repository inventory;
- preflight orchestration.

Metadata declares architecture-only maturity with empty implemented domain capability and claim inventories.

- Use the exact environment in [Contributing](CONTRIBUTING.md).
- Full CI and preflight belong in CI or in an explicitly admitted pre-push environment.
- See [Validation](VALIDATION.md) for the maintained validation scope.

## Intended evidence

Every future domain artefact will carry the platform's common provenance envelope, its source and environment digests, its confidentiality compartment and its explicit verification boundary. None of the planned record schemas is registered or qualified by this foundation.

## Documentation and support

Read [Architecture](ARCHITECTURE.md), [support](SUPPORT.md), [security reporting](SECURITY.md) and [citation metadata](CITATION.cff).

**Not claimed:**
- a hosted service, released package or DOI;
- a public CI status;
- a performed simulation, hardware measurement or sign-off verdict.

## Licence

Source is licensed under [AGPL-3.0-or-later](LICENSE). A commercial licence is available through the contact in [NOTICE](NOTICE.md).

![ANULUM](docs/assets/anulum_logo_company.jpg)

![Fortis Studio](docs/assets/fortis_studio_logo.jpg)

## Text and data mining reservation
The rightsholder, Miroslav Šotek (ANULUM), expressly reserves the use of the
works in this repository for text and data mining, including the collection of
this content for, and its use in, training, fine-tuning or evaluating machine
learning and artificial intelligence models, in accordance with Article 4(3) of
Directive (EU) 2019/790 and the national provisions transposing it.

No permission for such use has been granted beyond what the licence in
`LICENSE` grants. This reservation does not change that licence: uses the
licence permits remain permitted on its terms, including its attribution and
share-alike conditions.

Reservation made on 2026-11-22. Requests for permission: contact the
rightsholder through the contact listed in this repository.
