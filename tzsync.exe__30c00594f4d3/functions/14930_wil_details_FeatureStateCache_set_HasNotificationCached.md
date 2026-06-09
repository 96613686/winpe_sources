# wil_details_FeatureStateCache::set_HasNotificationCached

- ea: `0x14930`
- end: `0x14947`
- name: `wil_details_FeatureStateCache::set_HasNotificationCached`
- size: `23`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x12fe0`
- `0x13100`

## callees

- `0x156c0`

## pseudocode

```c

```

## disassembly

```asm
0x14930  ldarg.0
0x14931  ldflda   valuetype AnonymousStructure wil_details_FeatureStateCache::Anonymous
0x14936  ldflda   valuetype AnonymousUnion1 AnonymousStructure::Union
0x1493b  ldflda   valuetype AnonymousUnion2 AnonymousUnion1::Union
0x14940  ldarg.1
0x14941  call     instance void AnonymousUnion2::set_HasNotificationCached(bool value)
0x14946  ret
```
