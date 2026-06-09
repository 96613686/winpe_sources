# Details::wil_details_FeatureStateCache_ReevaluateCachedVariantState

- ea: `0x13100`
- end: `0x131c7`
- name: `Details::wil_details_FeatureStateCache_ReevaluateCachedVariantState`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: ``

## callers

- `0x128c0`

## callees

- `0xdb0`
- `0x13100`
- `0x131d0`
- `0x14910`
- `0x14930`
- `0x14950`
- `0x14970`
- `0x14a90`
- `0x14ab0`
- `0x14ad0`
- `0x14af0`
- `0x14b10`
- `0x14b30`
- `0x14b50`
- `0x14b60`
- `0x14be0`

## pseudocode

```c

```

## disassembly

```asm
0x13100  ldloca.s 0
0x13102  initobj  wil_details_FeatureStateCache
0x13108  ldc.i4.0
0x13109  stloc.3
0x1310a  ldc.i4.0
0x1310b  stloc.s  4
0x1310d  ldarg.1
0x1310e  ldobj    wil_details_FeatureStateCache
0x13113  stloc.1
0x13114  ldarg.2
0x13115  ldloca.s 4
0x13117  call     valuetype wil_details_FeatureStateCache Details::wil_details_GetCurrentVariantState(valuetype wil_details_FeatureDescriptor& descriptor, [out] bool& cacheVariantState)
0x1311c  stloc.2
0x1311d  ldarg.2
0x1311e  call     instance valuetype wil_FeatureChangeTime wil_details_FeatureDescriptor::get_ChangeTime()
0x13123  brtrue.s loc_1312B
0x13125  ldloc.3
0x13126  brtrue.s loc_1312B
0x13128  ldc.i4.0
0x13129  stloc.s  4
0x1312b  ldloca.s 0
0x1312d  ldloc.1
0x1312e  ldfld    int64 wil_details_FeatureStateCache::Exchange64
0x13133  stfld    int64 wil_details_FeatureStateCache::Exchange64
0x13138  ldloca.s 1
0x1313a  ldloc.0
0x1313b  ldfld    int64 wil_details_FeatureStateCache::Exchange64
0x13140  stfld    int64 wil_details_FeatureStateCache::Exchange64
0x13145  ldloca.s 1
0x13147  call     instance bool wil_details_FeatureStateCache::get_VariantCached()
0x1314c  brtrue.s loc_13181
0x1314e  ldloca.s 1
0x13150  ldloca.s 2
0x13152  call     instance int32 wil_details_FeatureStateCache::get_Variant()
0x13157  call     instance void wil_details_FeatureStateCache::set_Variant(int32 value)
0x1315c  ldloca.s 1
0x1315e  ldloca.s 2
0x13160  call     instance int32 wil_details_FeatureStateCache::get_PayloadId()
0x13165  call     instance void wil_details_FeatureStateCache::set_PayloadId(int32 value)
0x1316a  ldloca.s 1
0x1316c  ldloca.s 2
0x1316e  call     instance bool wil_details_FeatureStateCache::get_IsWexpConfiguration()
0x13173  call     instance void wil_details_FeatureStateCache::set_IsWexpConfiguration(bool value)
0x13178  ldloca.s 1
0x1317a  ldloc.s  4
0x1317c  call     instance void wil_details_FeatureStateCache::set_VariantCached(bool value)
0x13181  ldloca.s 0
0x13183  call     instance bool wil_details_FeatureStateCache::get_HasNotificationCached()
0x13188  brtrue.s loc_131A0
0x1318a  ldloca.s 1
0x1318c  ldloca.s 2
0x1318e  call     instance bool wil_details_FeatureStateCache::get_HasNotification()
0x13193  call     instance void wil_details_FeatureStateCache::set_HasNotification(bool value)
0x13198  ldloca.s 1
0x1319a  ldc.i4.1
0x1319b  call     instance void wil_details_FeatureStateCache::set_HasNotificationCached(bool value)
0x131a0  ldarg.0
0x131a1  ldflda   int64 wil_details_FeatureStateCache::Exchange64
0x131a6  ldloca.s 0
0x131a8  ldflda   int64 wil_details_FeatureStateCache::Exchange64
0x131ad  ldloc.1
0x131ae  ldfld    int64 wil_details_FeatureStateCache::Exchange64
0x131b3  call     bool Microsoft.Internal.PInvoke.Util.InterlockedHelper::CompareExchange(int64& obj, int64& expected, int64 desired)
0x131b8  brfalse  loc_13138
0x131bd  ldloca.s 0
0x131bf  call     instance bool wil_details_FeatureStateCache::get_HasNotificationCached()
0x131c4  pop
0x131c5  ldloc.1
0x131c6  ret
```
