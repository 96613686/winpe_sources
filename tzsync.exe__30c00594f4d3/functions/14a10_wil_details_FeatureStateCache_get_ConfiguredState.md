# wil_details_FeatureStateCache::get_ConfiguredState

- ea: `0x14a10`
- end: `0x14a26`
- name: `wil_details_FeatureStateCache::get_ConfiguredState`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x12fe0`
- `0x13390`

## callees

- `0x15760`

## pseudocode

```c

```

## disassembly

```asm
0x14a10  ldarg.0
0x14a11  ldflda   valuetype AnonymousStructure wil_details_FeatureStateCache::Anonymous
0x14a16  ldflda   valuetype AnonymousUnion1 AnonymousStructure::Union
0x14a1b  ldflda   valuetype AnonymousUnion2 AnonymousUnion1::Union
0x14a20  call     instance valuetype wil_FeatureEnabledState AnonymousUnion2::get_ConfiguredState()
0x14a25  ret
```
