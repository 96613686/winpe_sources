# wil_details_FeatureStateCache::get_HasNotification

- ea: `0x14a90`
- end: `0x14aa6`
- name: `wil_details_FeatureStateCache::get_HasNotification`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x12fe0`
- `0x13100`

## callees

- `0x157e0`

## pseudocode

```c

```

## disassembly

```asm
0x14a90  ldarg.0
0x14a91  ldflda   valuetype AnonymousStructure wil_details_FeatureStateCache::Anonymous
0x14a96  ldflda   valuetype AnonymousUnion1 AnonymousStructure::Union
0x14a9b  ldflda   valuetype AnonymousUnion2 AnonymousUnion1::Union
0x14aa0  call     instance bool AnonymousUnion2::get_HasNotification()
0x14aa5  ret
```
