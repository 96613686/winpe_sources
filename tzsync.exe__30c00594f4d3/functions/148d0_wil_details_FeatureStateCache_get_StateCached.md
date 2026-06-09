# wil_details_FeatureStateCache::get_StateCached

- ea: `0x148d0`
- end: `0x148e6`
- name: `wil_details_FeatureStateCache::get_StateCached`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x12890`
- `0x12fe0`

## callees

- `0x15660`

## pseudocode

```c

```

## disassembly

```asm
0x148d0  ldarg.0
0x148d1  ldflda   valuetype AnonymousStructure wil_details_FeatureStateCache::Anonymous
0x148d6  ldflda   valuetype AnonymousUnion1 AnonymousStructure::Union
0x148db  ldflda   valuetype AnonymousUnion2 AnonymousUnion1::Union
0x148e0  call     instance bool AnonymousUnion2::get_StateCached()
0x148e5  ret
```
