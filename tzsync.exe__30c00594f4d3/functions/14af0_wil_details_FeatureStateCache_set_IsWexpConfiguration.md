# wil_details_FeatureStateCache::set_IsWexpConfiguration

- ea: `0x14af0`
- end: `0x14b07`
- name: `wil_details_FeatureStateCache::set_IsWexpConfiguration`
- size: `23`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x12fe0`
- `0x13100`
- `0x131d0`
- `0x13390`

## callees

- `0x15840`

## pseudocode

```c

```

## disassembly

```asm
0x14af0  ldarg.0
0x14af1  ldflda   valuetype AnonymousStructure wil_details_FeatureStateCache::Anonymous
0x14af6  ldflda   valuetype AnonymousUnion1 AnonymousStructure::Union
0x14afb  ldflda   valuetype AnonymousUnion2 AnonymousUnion1::Union
0x14b00  ldarg.1
0x14b01  call     instance void AnonymousUnion2::set_IsWexpConfiguration(bool value)
0x14b06  ret
```
