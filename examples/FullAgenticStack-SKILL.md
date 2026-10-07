# FullAgenticStack RFC Skills

This is an example of the Skill produced from the RFC corpus in [FullAgenticStack/docs/RFCs](https://github.com/suissa/FullAgenticStack/tree/943dd66e8e628cbae1640ab9aa40d7d029bb1d87/docs/RFCs).

## When to use

Use this Skill when implementing, reviewing, testing or modifying a system that claims conformance with FullAgenticStack RFCs.

## Mandatory reading order

1. [RFC index](https://github.com/suissa/FullAgenticStack/blob/943dd66e8e628cbae1640ab9aa40d7d029bb1d87/docs/RFCs/README.md)
2. Applicable `semantic.md` files
3. Paired `implementation/README.md`
4. `implementation/architecture.mmd`
5. `implementation/technology.yml`
6. `implementation/bindings.yml`
7. `implemented/manifest.yml`
8. `implemented/evidence.yml`
9. `implemented/tests.yml`
10. `implemented/conformance.zig` when executable conformance is required

## Operational rule

`semantic.md` answers **what must be true**.

`implementation/*` answers **how the reference implementation realizes it**.

`implemented/*` answers **how we know it is true**.

Never reverse these authorities.

## RFC selection

The corpus currently contains RFC-FAS-0000 through RFC-FAS-0017. Select the smallest set of applicable RFCs, then load their semantic files before changing code.

## Example: RFC-FAS-0002

For an Intent-related task, load [RFC-FAS-0002 semantic.md](https://github.com/suissa/FullAgenticStack/blob/943dd66e8e628cbae1640ab9aa40d7d029bb1d87/docs/RFCs/RFC-FAS-0002-Intent-as-Universal-Interface/semantic.md), then its [implementation profile](https://github.com/suissa/FullAgenticStack/tree/943dd66e8e628cbae1640ab9aa40d7d029bb1d87/docs/RFCs/RFC-FAS-0002-Intent-as-Universal-Interface/implementation).

Before implementation, identify the relevant requirements and their evidence. During implementation, preserve their semantics. After implementation, evaluate the conformance artifacts.

## Failure behavior

If a semantic requirement and an implementation artifact disagree, preserve `semantic.md` and report the conflict.

If evidence is missing, the capability is not proven merely because the implementation exists.
