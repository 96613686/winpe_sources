# wil_details_FeatureStateCache::set_ConfiguredState

- ea: `0x14a30`
- end: `0x14a47`
- name: `wil_details_FeatureStateCache::set_ConfiguredState`
- size: `23`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x12fe0`
- `0x131d0`
- `0x13390`

## callees

- `0x15780`

## pseudocode

```c

```

## disassembly

```asm
0x14a30  ldarg.0
0x14a31  ldflda   valuetype AnonymousStructure wil_details_FeatureStateCache::Anonymous
0x14a36  ldflda   valuetype AnonymousUnion1 AnonymousStructure::Union
0x14a3b  ldflda   valuetype AnonymousUnion2 AnonymousUnion1::Union
0x14a40  ldarg.1
0x14a41  call     instance void AnonymousUnion2::set_ConfiguredState(valuetype wil_FeatureEnabledState value)
0x14a46  ret
```
