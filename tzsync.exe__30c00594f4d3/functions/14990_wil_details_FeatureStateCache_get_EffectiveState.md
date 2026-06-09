# wil_details_FeatureStateCache::get_EffectiveState

- ea: `0x14990`
- end: `0x149a6`
- name: `wil_details_FeatureStateCache::get_EffectiveState`
- size: `22`
- prototype: ``
- caller_count: `117`
- callee_count: `1`
- tags: ``

## callers

- `0x1120`
- `0x12d0`
- `0x1480`
- `0x1600`
- `0x1780`
- `0x1900`
- `0x1a90`
- `0x1c20`
- `0x1db0`
- `0x1f30`
- `0x20b0`
- `0x2250`
- `0x23f0`
- `0x2590`
- `0x2720`
- `0x28b0`
- `0x2a40`
- `0x2bd0`
- `0x2d60`
- `0x2ef0`
- `0x3080`
- `0x3210`
- `0x33a0`
- `0x3530`
- `0x36c0`
- `0x3850`
- `0x39e0`
- `0x3b70`
- `0x3d20`
- `0x3ed0`
- `0x4080`
- `0x4230`
- `0x43e0`
- `0x4590`
- `0x4740`
- `0x48f0`
- `0x4aa0`
- `0x4c50`
- `0x4e00`
- `0x4fb0`
- `0x5160`
- `0x5310`
- `0x54c0`
- `0x5670`
- `0x5820`
- `0x59d0`
- `0x5b60`
- `0x5ce0`
- `0x5e70`
- `0x6000`

## callees

- `0x15620`

## pseudocode

```c

```

## disassembly

```asm
0x14990  ldarg.0
0x14991  ldflda   valuetype AnonymousStructure wil_details_FeatureStateCache::Anonymous
0x14996  ldflda   valuetype AnonymousUnion1 AnonymousStructure::Union
0x1499b  ldflda   valuetype AnonymousUnion2 AnonymousUnion1::Union
0x149a0  call     instance bool AnonymousUnion2::get_EffectiveState()
0x149a5  ret
```
