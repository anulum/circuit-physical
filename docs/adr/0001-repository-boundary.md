<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-PHYSICAL — repository foundation
-->

# Decision: enforce post-dummy-fill timing, dual-DRC, ESD/substrate rules and shuttle-frame checks in Circuit Physical

## Context

Shuttle and ASIC tapeouts routinely fail from unbuffered macro hold paths, coupling added by metal dummy fill, unconnected macro power pins, `GDSII` cell-prefix collisions or backside-substrate bias mismatches.

## Decision

**What Circuit Physical owns:**
- physical operation;
- physical result;
- shuttle top harness specification;

**What it imports:** only Circuit Core and Circuit Technology.

**Owned elsewhere:**

| Responsibility | Owner |
|---|---|
| RTL synthesis and DFT manifests | Circuit Digital |
| SPICE jitter and analogue blocks | Circuit Analog |
| package, bondwire and PCB/3D stack | Circuit Assembly |
| tapeout sign-off verdicts | Circuit Acceptance |
| foundry tapeout package and wafer sort | Circuit Manufacturing |

## Consequences

**What can be qualified now:** repository governance and validation tooling, before domain code exists.

**What it cannot qualify:** unimplemented schemas, solvers, hardware or sign-off verdicts.

**Architectural consequences:**
- Circuit Physical owns RTL-to-GDSII operations, post-fill sign-off results and shuttle harness specifications;
- all copyleft physical-verification tools execute in separate processes;
- package die-attach and multi-die stack co-design stay separated in Circuit Assembly.
