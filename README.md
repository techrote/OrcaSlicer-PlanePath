# OrcaSlicer PlanePath

Research and implementation campaign for a custom OrcaSlicer build with **script-defined solid-fill plane paths**, including a growing library of printable space-filling curves.

This repository starts as a planning/RAG corpus and becomes the implementation fork according to the dependency-ordered GitHub issues.

## Core objective

Extend OrcaSlicer's existing `FillPlanePath` architecture so user-installable, sandboxed scripts can emit geometry into Orca's native clipping/spacing/flow/toolpath pipeline. Scripts describe path topology; Orca remains authoritative for printable geometry, extrusion and G-code.

Initial scope is **internal solid fill, top surfaces and bottom surfaces**. Sparse/scripted structural infill is deliberately deferred until the solid-fill architecture is proven.

## RAG corpus

Read `docs/rag/INDEX.md` first. It routes implementation agents to:

- project scope and non-goals;
- current OrcaSlicer seam map;
- target architecture and invariants;
- script ABI and sandbox model;
- pattern-trait/config/project-portability design;
- space-filling-curve research catalogue;
- test/CI strategy;
- reviewed dependency roadmap;
- autonomous issue/PR/merge contract.

## Governing principle

A custom pattern script must never become a G-code postprocessor. It produces bounded geometric path primitives; existing OrcaSlicer code remains responsible for clipping against printable surfaces, line/flow semantics, extrusion and final G-code.

## Upstream

Primary upstream: https://github.com/OrcaSlicer/OrcaSlicer

The planning corpus records source paths rather than assuming line numbers, because upstream moves continuously.
