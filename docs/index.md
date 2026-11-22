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

Circuit Physical is being built to run deterministic physical implementation from synthesised netlists to tapeout-ready `GDSII` or `OASIS` layouts — enforcing post-dummy-fill parasitic extraction and static timing, dual-tool design-rule checking, layout-versus-schematic equivalence, electrostatic-discharge and latch-up tie-offs, backside-substrate binding, failure-analysis fiducials and multi-project-wafer shuttle harness integration — completely without requiring AI. Its current executable surface is repository validation tooling. It has no installed place-and-route runner, static-timing engine, dual-DRC/LVS checker, shuttle harness builder or qualified record schema.

Read [Architecture](ARCHITECTURE.md), [validation tooling](validation-tooling.md), [data boundaries](THREAT_MODEL.md) and the [repository boundary decision](adr/0001-repository-boundary.md).
