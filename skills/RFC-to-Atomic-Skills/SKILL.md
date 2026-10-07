# RFC-to-Atomic-Skills Skill

Use this Skill when an Agent must convert a Semantic RFC folder into reusable Atomic Skills.

## Source model

Read [SRFC-to-Atomic-Skills](../../docs/SRFC-to-Atomic-Skills.md) first.

Then inspect the source RFC:

1. [semantic.md](../../../FullAgenticStack/docs/RFCs/README.md) — normative semantics.
2. `implementation/README.md` — reference procedure.
3. `implementation/architecture.mmd` — ownership/topology.
4. `implementation/technology.yml` — concrete binding.
5. `implementation/bindings.yml` — traceability.
6. `implemented/manifest.yml` — normalized requirements.
7. `implemented/evidence.yml` — proof.
8. `implemented/tests.yml` — verification.
9. `implemented/conformance.zig` — executable conformance.

## Procedure

1. Determine the RFC scope.
2. Enumerate normative requirements from `semantic.md`.
3. Group requirements into independently reusable capabilities.
4. For each capability create exactly one Atomic Skill.
5. Copy semantic constraints into the Atomic Skill; never weaken them.
6. Link the Atomic Skill to its source requirement and implementation artifacts.
7. Add evidence and conformance references.
8. Create/update the parent `SKILL.md`.
9. The parent Skill must explain when to invoke each Atomic Skill and in which order.
10. Validate that every normative requirement is covered by at least one Atomic Skill.

## Atomic Skill quality gate

Reject an Atomic Skill if it:

- has multiple unrelated responsibilities;
- has no source semantic link;
- has no trigger;
- has undefined inputs or outputs;
- loses an invariant;
- claims evidence without a reference;
- uses implementation details as semantic authority.

## Result

The desired result is:

```
semantic.md
   ↓
requirements
   ↓
Atomic Skills
   ↓
parent SKILL.md
   ↓
Agent execution
   ↓
evidence
   ↓
conformance
```
