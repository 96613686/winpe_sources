# Details::wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState

- ea: `0x12fe0`
- end: `0x130f4`
- name: `Details::wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState`
- size: `276`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: ``

## callers

- `0x12890`

## callees

- `0xdd0`
- `0x12fe0`
- `0x13390`
- `0x148d0`
- `0x148f0`
- `0x14910`
- `0x14930`
- `0x14990`
- `0x149b0`
- `0x149d0`
- `0x149f0`
- `0x14a10`
- `0x14a30`
- `0x14a90`
- `0x14ab0`
- `0x14ad0`
- `0x14af0`
- `0x14be0`

## pseudocode

```c

```

## disassembly

```asm
0x12fe0  ldloca.s 0
0x12fe2  initobj  wil_details_FeatureStateCache
0x12fe8  ldc.i4.0
0x12fe9  stloc.3
0x12fea  ldc.i4.0
0x12feb  stloc.s  4
0x12fed  ldarg.1
0x12fee  ldobj    wil_details_FeatureStateCache
0x12ff3  stloc.1
0x12ff4  ldarg.2
0x12ff5  ldloca.s 4
0x12ff7  call     valuetype wil_details_FeatureStateCache Details::wil_details_GetCurrentFeatureEnabledState(valuetype wil_details_FeatureDescriptor& descriptor, [out] bool& cacheFeatureState)
0x12ffc  stloc.2
0x12ffd  ldarg.2
0x12ffe  call     instance valuetype wil_FeatureChangeTime wil_details_FeatureDescriptor::get_ChangeTime()
0x13003  brtrue.s loc_1300B
0x13005  ldloc.3
0x13006  brtrue.s loc_1300B
0x13008  ldc.i4.0
0x13009  stloc.s  4
0x1300b  ldloca.s 0
0x1300d  ldloc.1
0x1300e  ldfld    int32 wil_details_FeatureStateCache::Exchange
0x13013  stfld    int32 wil_details_FeatureStateCache::Exchange
0x13018  ldloca.s 1
0x1301a  ldloc.0
0x1301b  ldfld    int32 wil_details_FeatureStateCache::Exchange
0x13020  stfld    int32 wil_details_FeatureStateCache::Exchange
0x13025  ldloc.s  4
0x13027  brfalse.s loc_13072
0x13029  ldloca.s 0
0x1302b  call     instance bool wil_details_FeatureStateCache::get_StateCached()
0x13030  brtrue.s loc_13072
0x13032  ldloca.s 1
0x13034  ldloca.s 2
0x13036  call     instance valuetype wil_FeatureEnabledState wil_details_FeatureStateCache::get_ConfiguredState()
0x1303b  call     instance void wil_details_FeatureStateCache::set_ConfiguredState(valuetype wil_FeatureEnabledState value)
0x13040  ldloca.s 1
0x13042  ldloca.s 2
0x13044  call     instance bool wil_details_FeatureStateCache::get_DesiredState()
0x13049  call     instance void wil_details_FeatureStateCache::set_DesiredState(bool value)
0x1304e  ldloca.s 1
0x13050  ldloca.s 2
0x13052  call     instance bool wil_details_FeatureStateCache::get_EffectiveState()
0x13057  call     instance void wil_details_FeatureStateCache::set_EffectiveState(bool value)
0x1305c  ldloca.s 1
0x1305e  ldloca.s 2
0x13060  call     instance bool wil_details_FeatureStateCache::get_IsWexpConfiguration()
0x13065  call     instance void wil_details_FeatureStateCache::set_IsWexpConfiguration(bool value)
0x1306a  ldloca.s 1
0x1306c  ldc.i4.1
0x1306d  call     instance void wil_details_FeatureStateCache::set_StateCached(bool value)
0x13072  ldloca.s 0
0x13074  call     instance bool wil_details_FeatureStateCache::get_HasNotificationCached()
0x13079  brtrue.s loc_13091
0x1307b  ldloca.s 1
0x1307d  ldloca.s 2
0x1307f  call     instance bool wil_details_FeatureStateCache::get_HasNotification()
0x13084  call     instance void wil_details_FeatureStateCache::set_HasNotification(bool value)
0x13089  ldloca.s 1
0x1308b  ldc.i4.1
0x1308c  call     instance void wil_details_FeatureStateCache::set_HasNotificationCached(bool value)
0x13091  ldarg.0
0x13092  ldflda   int32 wil_details_FeatureStateCache::Exchange
0x13097  ldloca.s 0
0x13099  ldflda   int32 wil_details_FeatureStateCache::Exchange
0x1309e  ldloc.1
0x1309f  ldfld    int32 wil_details_FeatureStateCache::Exchange
0x130a4  call     bool Microsoft.Internal.PInvoke.Util.InterlockedHelper::CompareExchange(int32& obj, int32& expected, int32 desired)
0x130a9  brfalse  loc_13018
0x130ae  ldloca.s 0
0x130b0  call     instance bool wil_details_FeatureStateCache::get_HasNotificationCached()
0x130b5  pop
0x130b6  ldloc.s  4
0x130b8  brtrue.s loc_130F2
0x130ba  ldloca.s 1
0x130bc  ldloca.s 2
0x130be  call     instance valuetype wil_FeatureEnabledState wil_details_FeatureStateCache::get_ConfiguredState()
0x130c3  call     instance void wil_details_FeatureStateCache::set_ConfiguredState(valuetype wil_FeatureEnabledState value)
0x130c8  ldloca.s 1
0x130ca  ldloca.s 2
0x130cc  call     instance bool wil_details_FeatureStateCache::get_DesiredState()
0x130d1  call     instance void wil_details_FeatureStateCache::set_DesiredState(bool value)
0x130d6  ldloca.s 1
0x130d8  ldloca.s 2
0x130da  call     instance bool wil_details_FeatureStateCache::get_EffectiveState()
0x130df  call     instance void wil_details_FeatureStateCache::set_EffectiveState(bool value)
0x130e4  ldloca.s 1
0x130e6  ldloca.s 2
0x130e8  call     instance bool wil_details_FeatureStateCache::get_IsWexpConfiguration()
0x130ed  call     instance void wil_details_FeatureStateCache::set_IsWexpConfiguration(bool value)
0x130f2  ldloc.1
0x130f3  ret
```
