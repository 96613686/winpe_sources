# wil_details_FeatureStateCache::get_IsWexpConfiguration

- ea: `0x14ad0`
- end: `0x14ae6`
- name: `wil_details_FeatureStateCache::get_IsWexpConfiguration`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x12fe0`
- `0x13100`

## callees

- `0x15820`

## pseudocode

```c

```

## disassembly

```asm
0x14ad0  ldarg.0
0x14ad1  ldflda   valuetype AnonymousStructure wil_details_FeatureStateCache::Anonymous
0x14ad6  ldflda   valuetype AnonymousUnion1 AnonymousStructure::Union
0x14adb  ldflda   valuetype AnonymousUnion2 AnonymousUnion1::Union
0x14ae0  call     instance bool AnonymousUnion2::get_IsWexpConfiguration()
0x14ae5  ret
```
