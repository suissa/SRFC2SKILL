# Semantic RFC (SRFC)

A Semantic RFC is an RFC whose primary artifact is an agent-readable semantic specification. In FullAgenticStack this artifact is `semantic.md`.

The important distinction is:

```
RFC prose      = explanation
semantic.md   = normative semantic authority
implementation/ = technology/reference projection
implemented/   = conformance evidence
```

The semantic file must describe the invariant meaning of the system independently of a particular implementation.

## What an SRFC defines

An SRFC should make these questions answerable:

1. What problem or capability is being specified?
2. What entities participate?
3. What behavior is required?
4. What is mandatory, permitted, forbidden, or conditional?
5. What invariants must always hold?
6. What evidence proves conformance?
7. What implementation artifacts explain the preferred projection?
8. How can an Agent discover the complete specification without guessing?

## Recommended semantic.md structure

```markdown
# RFC-FAS-NNNN — <Name>

## Status
...

## Intent
The semantic purpose of this RFC.

## Scope
What this RFC defines and what it does not define.

## Semantic Model
The nouns, relationships, actors and boundaries.

## Normative Requirements
- The system MUST ...
- An Agent MUST ...
- An implementation MUST NOT ...

## Invariants
- ...
- ...

## Behavior
1. ...
2. ...

## Evidence
- ...

## Conformance
A conforming implementation ...

## Non-goals
- ...

## Implementation Mapping
The paired implementation profile is authoritative for the reference technology only.
```

## Normative language

Use `MUST`, `MUST NOT`, `SHOULD`, `SHOULD NOT`, and `MAY` consistently. A sentence containing a normative keyword must be testable or mechanically attributable to evidence.

Prefer:

```
The Runtime MUST reject an Action when authority is absent.
```

over:

```
The Runtime should probably reject unauthorized Actions.
```

## Example

See [RFC-FAS-0002 semantic.md](https://github.com/suissa/FullAgenticStack/blob/943dd66e8e628cbae1640ab9aa40d7d029bb1d87/docs/RFCs/RFC-FAS-0002-Intent-as-Universal-Interface/semantic.md).

The complete canonical corpus is [FullAgenticStack/docs/RFCs](https://github.com/suissa/FullAgenticStack/tree/943dd66e8e628cbae1640ab9aa40d7d029bb1d87/docs/RFCs).
