# wil_details_FeatureStateCache::set_HasNotification

- ea: `0x14ab0`
- end: `0x14ac7`
- name: `wil_details_FeatureStateCache::set_HasNotification`
- size: `23`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x12fe0`
- `0x13100`
- `0x131d0`
- `0x13390`

## callees

- `0x15800`

## pseudocode

```c

```

## disassembly

```asm
0x14ab0  ldarg.0
0x14ab1  ldflda   valuetype AnonymousStructure wil_details_FeatureStateCache::Anonymous
0x14ab6  ldflda   valuetype AnonymousUnion1 AnonymousStructure::Union
0x14abb  ldflda   valuetype AnonymousUnion2 AnonymousUnion1::Union
0x14ac0  ldarg.1
0x14ac1  call     instance void AnonymousUnion2::set_HasNotification(bool value)
0x14ac6  ret
```
