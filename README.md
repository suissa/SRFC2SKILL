# SRFC2SKILL

SRFC2SKILL defines a deterministic path from a Semantic RFC (SRFC) to Agent Skills and Atomic Skills.

The canonical source analyzed by this project is the RFC system in [suissa/FullAgenticStack/docs/RFCs](https://github.com/suissa/FullAgenticStack/tree/943dd66e8e628cbae1640ab9aa40d7d029bb1d87/docs/RFCs).

## Core model

```
Semantic RFC
  -> semantic.md              normative meaning
  -> implementation/          preferred implementation projection
  -> implemented/             evidence and conformance
  -> Atomic Skills             smallest reusable capabilities
  -> SKILL.md                  orchestration and usage rules
```

SRFC2SKILL does not treat an RFC as a prompt. It treats the RFC as a semantic contract from which an Agent can derive what to do, when to do it, how to verify it, and which Atomic Skills are required.

## Reference

- [SRFC specification](docs/SRFC-Semantic-RFC.md)
- [RFC folder model](docs/SRFC-Folder-Model.md)
- [RFC -> Skill conversion](docs/SRFC-to-SKILL.md)
- [RFC -> Atomic Skills](docs/SRFC-to-Atomic-Skills.md)
- [example generated Skill](examples/FullAgenticStack-SKILL.md)
- [example Atomic Skill](examples/Atomic-Skill-Intent.md)
- [Atomic Skill generation Skill](skills/RFC-to-Atomic-Skills/SKILL.md)

The source RFC corpus is [FullAgenticStack/docs/RFCs](https://github.com/suissa/FullAgenticStack/tree/943dd66e8e628cbae1640ab9aa40d7d029bb1d87/docs/RFCs).
