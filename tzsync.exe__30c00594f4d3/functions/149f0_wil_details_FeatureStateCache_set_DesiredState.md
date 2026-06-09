# wil_details_FeatureStateCache::set_DesiredState

- ea: `0x149f0`
- end: `0x14a07`
- name: `wil_details_FeatureStateCache::set_DesiredState`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x12fe0`
- `0x13390`

## callees

- `0x15740`

## pseudocode

```c

```

## disassembly

```asm
0x149f0  ldarg.0
0x149f1  ldflda   valuetype AnonymousStructure wil_details_FeatureStateCache::Anonymous
0x149f6  ldflda   valuetype AnonymousUnion1 AnonymousStructure::Union
0x149fb  ldflda   valuetype AnonymousUnion2 AnonymousUnion1::Union
0x14a00  ldarg.1
0x14a01  call     instance void AnonymousUnion2::set_DesiredState(bool value)
0x14a06  ret
```
