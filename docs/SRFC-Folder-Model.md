# SRFC folder model

The analyzed FullAgenticStack corpus uses the same semantic-to-implementation-to-evidence shape across RFCs.

A typical RFC folder is:

```text
RFC-FAS-NNNN-Name/
├── semantic.md
├── implementation/
│   ├── README.md
│   ├── architecture.mmd
│   ├── technology.yml
│   └── bindings.yml
└── implemented/
    ├── conformance.zig
    ├── evidence.yml
    ├── manifest.yml
    └── tests.yml
```

This exact pattern is present across RFC-FAS-0000 through RFC-FAS-0017 in the analyzed revision of [FullAgenticStack/docs/RFCs](https://github.com/suissa/FullAgenticStack/tree/943dd66e8e628cbae1640ab9aa40d7d029bb1d87/docs/RFCs).

## File responsibilities

| File | Authority / role | How an Agent uses it |
|---|---|---|
| `semantic.md` | normative semantics | learn what MUST be true |
| `implementation/README.md` | implementation procedure/profile | learn how the reference implementation realizes the semantics |
| `implementation/architecture.mmd` | topology | understand component relationships |
| `implementation/technology.yml` | technology binding | identify concrete technologies and profiles |
| `implementation/bindings.yml` | traceability | map semantic source to implementation artifacts |
| `implemented/conformance.zig` | executable conformance | inspect or run semantic checks |
| `implemented/evidence.yml` | evidence metadata | identify proof/evidence |
| `implemented/manifest.yml` | requirement manifest | enumerate normalized requirements |
| `implemented/tests.yml` | test declarations | identify verification expectations |

## Important rule

`semantic.md` is the source of semantic truth. Implementation files may specialize it but must not silently redefine it.

This is explicitly reflected in the FullAgenticStack RFC system: `bindings.yml` points back to `../semantic.md`, and the RFC tooling treats `semantic.md` as the source of truth.

## Creation order

```
1. define semantic.md
2. derive implementation/README.md
3. derive architecture.mmd
4. bind technology.yml
5. bind traceability in bindings.yml
6. implement conformance
7. record evidence
8. generate manifest
9. define tests
```
