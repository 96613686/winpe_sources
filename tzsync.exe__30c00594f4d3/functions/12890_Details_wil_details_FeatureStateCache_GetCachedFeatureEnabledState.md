# Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState

- ea: `0x12890`
- end: `0x128bf`
- name: `Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState`
- size: `47`
- prototype: ``
- caller_count: `116`
- callee_count: `3`
- tags: ``

## callers

- `0x10e0`
- `0x1290`
- `0x1440`
- `0x15c0`
- `0x1740`
- `0x18c0`
- `0x1a50`
- `0x1be0`
- `0x1d70`
- `0x1ef0`
- `0x2070`
- `0x2210`
- `0x23b0`
- `0x2550`
- `0x26e0`
- `0x2870`
- `0x2a00`
- `0x2b90`
- `0x2d20`
- `0x2eb0`
- `0x3040`
- `0x31d0`
- `0x3360`
- `0x34f0`
- `0x3680`
- `0x3810`
- `0x39a0`
- `0x3b30`
- `0x3ce0`
- `0x3e90`
- `0x4040`
- `0x41f0`
- `0x43a0`
- `0x4550`
- `0x4700`
- `0x48b0`
- `0x4a60`
- `0x4c10`
- `0x4dc0`
- `0x4f70`
- `0x5120`
- `0x52d0`
- `0x5480`
- `0x5630`
- `0x57e0`
- `0x5990`
- `0x5b20`
- `0x5ca0`
- `0x5e30`
- `0x5fc0`

## callees

- `0x12890`
- `0x12fe0`
- `0x148d0`

## pseudocode

```c

```

## disassembly

```asm
0x12890  ldloca.s 0
0x12892  initobj  wil_details_FeatureStateCache
0x12898  ldloca.s 0
0x1289a  ldarg.0
0x1289b  ldflda   int32 wil_details_FeatureStateCache::Exchange
0x128a0  call     int32 [mscorlib]System.Threading.Volatile::Read(int32&)
0x128a5  stfld    int32 wil_details_FeatureStateCache::Exchange
0x128aa  ldloca.s 0
0x128ac  call     instance bool wil_details_FeatureStateCache::get_StateCached()
0x128b1  brfalse.s loc_128B5
0x128b3  ldloc.0
0x128b4  ret
0x128b5  ldarg.0
0x128b6  ldloca.s 0
0x128b8  ldarg.1
0x128b9  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureStateCache& observedState, valuetype wil_details_FeatureDescriptor& descriptor)
0x128be  ret
```
