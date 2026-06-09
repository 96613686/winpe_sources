# Details::wil_details_FeatureStateCache_GetCachedVariantState

- ea: `0x128c0`
- end: `0x128f0`
- name: `Details::wil_details_FeatureStateCache_GetCachedVariantState`
- size: `48`
- prototype: ``
- caller_count: `114`
- callee_count: `3`
- tags: ``

## callers

- `0x1100`
- `0x12b0`
- `0x1460`
- `0x15e0`
- `0x1760`
- `0x18e0`
- `0x1a70`
- `0x1c00`
- `0x1d90`
- `0x1f10`
- `0x2090`
- `0x2230`
- `0x23d0`
- `0x2570`
- `0x2700`
- `0x2890`
- `0x2a20`
- `0x2bb0`
- `0x2d40`
- `0x2ed0`
- `0x3060`
- `0x31f0`
- `0x3380`
- `0x3510`
- `0x36a0`
- `0x3830`
- `0x39c0`
- `0x3b50`
- `0x3d00`
- `0x3eb0`
- `0x4060`
- `0x4210`
- `0x43c0`
- `0x4570`
- `0x4720`
- `0x48d0`
- `0x4a80`
- `0x4c30`
- `0x4de0`
- `0x4f90`
- `0x5140`
- `0x52f0`
- `0x54a0`
- `0x5650`
- `0x5800`
- `0x59b0`
- `0x5b40`
- `0x5cc0`
- `0x5e50`
- `0x5fe0`

## callees

- `0x128c0`
- `0x13100`
- `0x14950`

## pseudocode

```c

```

## disassembly

```asm
0x128c0  ldloca.s 0
0x128c2  initobj  wil_details_FeatureStateCache
0x128c8  ldloca.s 0
0x128ca  ldflda   int64 wil_details_FeatureStateCache::Exchange64
0x128cf  ldarg.0
0x128d0  ldfld    int64 wil_details_FeatureStateCache::Exchange64
0x128d5  call     int64 [mscorlib]System.Threading.Interlocked::Exchange(int64&, int64)
0x128da  pop
0x128db  ldloca.s 0
0x128dd  call     instance bool wil_details_FeatureStateCache::get_VariantCached()
0x128e2  brfalse.s loc_128E6
0x128e4  ldloc.0
0x128e5  ret
0x128e6  ldarg.0
0x128e7  ldloca.s 0
0x128e9  ldarg.1
0x128ea  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_ReevaluateCachedVariantState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureStateCache& observedState, valuetype wil_details_FeatureDescriptor& descriptor)
0x128ef  ret
```
