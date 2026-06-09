# wil_details_FeatureStateCache::set_EffectiveState

- ea: `0x149b0`
- end: `0x149c7`
- name: `wil_details_FeatureStateCache::set_EffectiveState`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x12fe0`
- `0x13390`

## callees

- `0x15640`

## pseudocode

```c

```

## disassembly

```asm
0x149b0  ldarg.0
0x149b1  ldflda   valuetype AnonymousStructure wil_details_FeatureStateCache::Anonymous
0x149b6  ldflda   valuetype AnonymousUnion1 AnonymousStructure::Union
0x149bb  ldflda   valuetype AnonymousUnion2 AnonymousUnion1::Union
0x149c0  ldarg.1
0x149c1  call     instance void AnonymousUnion2::set_EffectiveState(bool value)
0x149c6  ret
```
