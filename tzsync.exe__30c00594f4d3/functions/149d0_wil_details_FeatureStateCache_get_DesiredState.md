# wil_details_FeatureStateCache::get_DesiredState

- ea: `0x149d0`
- end: `0x149e6`
- name: `wil_details_FeatureStateCache::get_DesiredState`
- size: `22`
- prototype: ``
- caller_count: `23`
- callee_count: `1`
- tags: ``

## callers

- `0x1060`
- `0x1210`
- `0x13c0`
- `0x3c60`
- `0x3e10`
- `0x3fc0`
- `0x4170`
- `0x4320`
- `0x44d0`
- `0x4680`
- `0x4830`
- `0x49e0`
- `0x4b90`
- `0x4d40`
- `0x4ef0`
- `0x50a0`
- `0x5250`
- `0x5400`
- `0x55b0`
- `0x5760`
- `0x5910`
- `0x12fe0`
- `0x13390`

## callees

- `0x15720`

## pseudocode

```c

```

## disassembly

```asm
0x149d0  ldarg.0
0x149d1  ldflda   valuetype AnonymousStructure wil_details_FeatureStateCache::Anonymous
0x149d6  ldflda   valuetype AnonymousUnion1 AnonymousStructure::Union
0x149db  ldflda   valuetype AnonymousUnion2 AnonymousUnion1::Union
0x149e0  call     instance bool AnonymousUnion2::get_DesiredState()
0x149e5  ret
```
