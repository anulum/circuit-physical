<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-PHYSICAL — repository foundation
-->

# Architecture

## Current executable surface

The checkout contains:
- repository validation tooling;
- dedicated tests;
- workflow definitions;
- native documentation.

No domain component of Circuit Physical is implemented yet. The metadata keeps domain capabilities, claims and qualified record formats empty.

## Intended data flow

1. **Floorplan, placement, clock tree and routing** map the synthesised netlist, DFT chains, ROM macros and analogue/photonic blocks onto the target metal stack.
2. **Dummy fill, post-fill extraction and static timing** insert foundry density fill outside exclusion zones, extract parasitics and verify setup, hold and macro boundary margins using analogue-derived clock jitter.
3. **Dual-DRC, LVS, ESD and shuttle integration** run `Magic` and `KLayout` DRC, `Netgen` LVS, `HBM`/`CDM` ESD, latch-up tie-off, substrate-potential, failure-analysis fiducial and cell-prefix collision checks.
4. **Metal-fix respin** applies bounded engineering-change layouts triggered by post-silicon corrective-action records.

## Ownership

**This project owns** the planned Circuit Physical records and boundary rules.

**Owned elsewhere:**

| Responsibility | Owner |
|---|---|
| RTL synthesis and DFT manifests | Circuit Digital |
| SPICE jitter and analogue blocks | Circuit Analog |
| package, bondwire and PCB/3D stack | Circuit Assembly |
| tapeout sign-off verdicts | Circuit Acceptance |
| foundry tapeout package and wafer sort | Circuit Manufacturing |

## Interpretation

- **Rule decks.** Passing open-deck DRC/LVS checks only the rules encoded in those decks.

Read [the documentation architecture](docs/ARCHITECTURE.md) for the planned records, domain rules and schema identifiers.
