# wil_details_FeatureStateCache::get_HasNotificationCached

- ea: `0x14910`
- end: `0x14926`
- name: `wil_details_FeatureStateCache::get_HasNotificationCached`
- size: `22`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x12fe0`
- `0x13100`

## callees

- `0x156a0`

## pseudocode

```c

```

## disassembly

```asm
0x14910  ldarg.0
0x14911  ldflda   valuetype AnonymousStructure wil_details_FeatureStateCache::Anonymous
0x14916  ldflda   valuetype AnonymousUnion1 AnonymousStructure::Union
0x1491b  ldflda   valuetype AnonymousUnion2 AnonymousUnion1::Union
0x14920  call     instance bool AnonymousUnion2::get_HasNotificationCached()
0x14925  ret
```
