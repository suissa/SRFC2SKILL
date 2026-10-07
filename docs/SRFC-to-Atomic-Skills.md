# SRFC -> Atomic Skills

An Atomic Skill is the smallest reusable capability that an Agent can invoke while preserving the semantics of its source RFC.

Do not mechanically create one Atomic Skill per RFC file. Extract capabilities from the semantic requirements.

## Extraction algorithm

```
1. Read semantic.md.
2. Normalize every MUST/MUST NOT/SHOULD requirement.
3. Group requirements by capability.
4. Identify input, output, preconditions, postconditions and evidence.
5. Use implementation/README.md to document the preferred procedure.
6. Use architecture.mmd to document ownership and boundaries.
7. Use technology.yml only for concrete bindings.
8. Use bindings.yml to preserve source traceability.
9. Use implemented/* to attach proof.
10. Emit one Atomic Skill per independently reusable capability.
11. Emit a parent SKILL.md that teaches selection and composition.
```

## Atomic Skill contract

Each Atomic Skill should contain:

```markdown
# Atomic Skill: <name>

## Source
[semantic.md](../../...)

## Purpose
One capability, one semantic responsibility.

## When to use
Trigger conditions.

## Inputs
...

## Preconditions
...

## Procedure
1. ...
2. ...

## Outputs
...

## Invariants
...

## Evidence
...

## Forbidden
...

## Implementation references
- [implementation/README.md](...)
- [architecture.mmd](...)
- [technology.yml](...)

## Conformance references
- [bindings.yml](...)
- [manifest.yml](...)
- [evidence.yml](...)
- [tests.yml](...)
```

## Example mapping

For RFC-FAS-0002, an Agent could derive capabilities such as:

```text
IntentRecognition
IntentNormalization
IntentPreservation
IntentRouting
IntentValidation
```

The exact names must be derived from the semantic requirements actually present in the RFC, not invented from implementation details.

Each Atomic Skill must link back to the exact semantic source and to the implementation/evidence artifacts used to justify it.

## Parent Skill

The parent `SKILL.md` is the selector and composer. It explains:

```
request
  -> identify applicable RFC
  -> identify required Atomic Skills
  -> execute Atomic Skills in semantic order
  -> collect evidence
  -> verify conformance
```

This preserves traceability:

```
RFC requirement -> Atomic Skill -> execution -> evidence -> conformance
```
