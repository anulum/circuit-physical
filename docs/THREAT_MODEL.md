<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-PHYSICAL — repository foundation
-->

# Data and authority boundaries

## Present tooling

**Execution inputs.** The maintained checkout and the selected development environment are what the repository controls inspect.

**Received inputs.** Descriptors, dependency receipts and generated inventories cannot nominate an acceptance policy or an executable.

**Bounded checks.** Controls inspect bounded local paths and emit fixed diagnostics.

Foundation qualification is in progress.

## Future domain inputs

**Supplied data, with no authority.** The following inputs are treated strictly as supplied data:
- gate-level netlists, timing constraints and scan manifests;
- macro `LEF`/`GDSII`/`OASIS` views and shuttle frames;
- foundry rule decks and waiver requests.

They grant no authority to:
- accept pre-fill timing or single-tool DRC as tapeout sign-off;
- grant a foundry DRC waiver without dual person-in-role approval;
- link copyleft EDA libraries in-process or export confidential foundry layouts;
- release a mask set to a foundry or spend.

**Comments and embedded text are data.** Descriptions, netlist comments and datasheets arriving inside supplied inputs are data, never instructions to an operator or an agent.

**Public-repository data boundary.** Hosted CI for this public repository runs on public material only. Confidential foundry-NDA, customer, export-controlled or secret-bearing material never enters this repository, its CI or its issues.

## Threats and the rules that answer them

| Threat | Architectural rule |
| --- | --- |
| Pre-fill timing closure invalidated by metal dummy fill or macro hold violations | Sign-off ordering enforces metal dummy fill (with sensitive-region exclusions) before final parasitic extraction, static timing and wrapper/macro hold-margin checks, driven by analogue-derived jitter bounds |
| Single-deck DRC blind spots, ESD/latch-up omissions, substrate shorts or cell-name collisions | Layouts require `Magic`-versus-`KLayout` dual-DRC consensus, `Netgen` LVS, `HBM`/`CDM` ESD and power-on-control tie-offs, explicit backside-substrate net binding, failure-analysis fiducials, `GDSII` cell-prefix checks and dual person-approved foundry waivers |
| Copyleft licence contamination or confidential `GDSII` exfiltration | `OpenSTA`, `OpenROAD`, `KLayout` and `Netgen` run strictly in separate processes, and confidential foundry layouts stay inside air-gapped enclave compartments |

## Residuals named, not removed

- **Foundry parasitic deck fidelity.** Open-PDK extraction decks approximate foundry corner capacitance and resistance within their published characterisation limits.

**Not claimed:** no isolation, physical, statistical, safety or durability guarantee is claimed by this foundation.
