# wil_details_FeatureStateCache::set_Variant

- ea: `0x14b30`
- end: `0x14b47`
- name: `wil_details_FeatureStateCache::set_Variant`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x13100`
- `0x131d0`

## callees

- `0x15880`

## pseudocode

```c

```

## disassembly

```asm
0x14b30  ldarg.0
0x14b31  ldflda   valuetype AnonymousStructure wil_details_FeatureStateCache::Anonymous
0x14b36  ldflda   valuetype AnonymousUnion1 AnonymousStructure::Union
0x14b3b  ldflda   valuetype AnonymousUnion2 AnonymousUnion1::Union
0x14b40  ldarg.1
0x14b41  call     instance void AnonymousUnion2::set_Variant(int32 value)
0x14b46  ret
```
