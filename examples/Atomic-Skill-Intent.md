# Atomic Skill: Intent Semantic Capability

## Source

- [RFC-FAS-0002 semantic.md](https://github.com/suissa/FullAgenticStack/blob/943dd66e8e628cbae1640ab9aa40d7d029bb1d87/docs/RFCs/RFC-FAS-0002-Intent-as-Universal-Interface/semantic.md)
- [RFC-FAS-0002 implementation](https://github.com/suissa/FullAgenticStack/tree/943dd66e8e628cbae1640ab9aa40d7d029bb1d87/docs/RFCs/RFC-FAS-0002-Intent-as-Universal-Interface/implementation)
- [RFC-FAS-0002 manifest/evidence](https://github.com/suissa/FullAgenticStack/tree/943dd66e8e628cbae1640ab9aa40d7d029bb1d87/docs/RFCs/RFC-FAS-0002-Intent-as-Universal-Interface/implemented)

## Purpose

Provide the reusable semantic capability for handling an Intent according to RFC-FAS-0002.

## When to use

Invoke when a task enters or modifies the Intent boundary defined by RFC-FAS-0002.

## Procedure

1. Read the RFC semantic source.
2. Determine the canonical Intent.
3. Preserve the Intent across the applicable runtime boundary.
4. Apply the RFC invariants.
5. Produce the evidence required by the RFC.
6. Check the implementation against its conformance artifacts.

## Inputs

A semantically classified Intent and its context.

## Outputs

A valid Intent representation suitable for the next semantic stage.

## Forbidden

Do not invent a new Intent meaning from a framework, route, database model or UI implementation.

## Traceability

This Atomic Skill is deliberately linked to the RFC instead of duplicating its normative text. The RFC remains the semantic authority.
