# Converting an SRFC into a SKILL

A generated Skill is not a copy of an RFC. It is an operational reading guide for an Agent.

The transformation is:

```
SRFC
  semantic.md
       ↓ what must be true
  implementation/README.md
       ↓ how to realize it
  architecture.mmd
       ↓ where responsibilities live
  technology.yml
       ↓ which concrete profile applies
  bindings.yml
       ↓ where each semantic requirement is bound
  implemented/*
       ↓ how conformance is proven
  SKILL.md
       ↓ when/how the Agent uses the complete system
```

## Required behavior of the generated SKILL.md

A Skill must tell the Agent:

- when the RFC applies;
- which files are mandatory to read first;
- which file answers which question;
- which semantic requirements are non-negotiable;
- which implementation artifacts are reference guidance rather than semantic authority;
- how to trace a requirement to evidence;
- when an Atomic Skill should be invoked;
- how to detect a missing, contradictory or unverifiable requirement.

## File-by-file usage

### semantic.md

Read first. Extract scope, actors, behaviors, invariants, normative requirements and forbidden behavior.

Never use an implementation artifact to override a semantic requirement.

### implementation/README.md

Read after the semantic file. Use it to understand the preferred realization and implementation decisions.

### architecture.mmd

Use when deciding component ownership, boundaries, dependencies and flow.

Do not infer new semantics from the diagram.

### technology.yml

Use when the task requires a concrete technology choice or reference profile.

Treat it as a binding, not as a replacement for semantic intent.

### bindings.yml

Use for traceability. It tells the Agent which semantic source and implementation artifacts belong together.

### implemented/conformance.zig

Use when conformance must be checked mechanically.

### evidence.yml

Use to locate the evidence that supports a requirement.

### manifest.yml

Use as the normalized requirement inventory.

### tests.yml

Use to understand verification expectations and test coverage.

## Minimal generated Skill

```markdown
# RFC-FAS-NNNN Skill

## When to use
Use this Skill whenever the task touches RFC-FAS-NNNN.

## Read order
1. [semantic.md](../semantic.md)
2. [implementation/README.md](../implementation/README.md)
3. [implementation/architecture.mmd](../implementation/architecture.mmd)
4. [implementation/technology.yml](../implementation/technology.yml)
5. [implementation/bindings.yml](../implementation/bindings.yml)
6. [implemented/manifest.yml](../implemented/manifest.yml)
7. [implemented/evidence.yml](../implemented/evidence.yml)
8. [implemented/tests.yml](../implemented/tests.yml)

## Execution rule
Satisfy semantic requirements first. Use implementation files to choose how to satisfy them. Verify the result against the implemented evidence and tests.

## Failure rule
If an implementation conflicts with semantic.md, stop and report the semantic conflict instead of changing the requirement.
```

The generated Skill therefore acts as an operational index over the RFC, not as a second source of truth.
