# Microsoft.Windows.Staging.Features.Feature_LocPerfVal::Feature_LocPerfVal__private_GetCachedFeatureEnabledState

- ea: `0x4a60`
- end: `0x4a75`
- name: `Microsoft.Windows.Staging.Features.Feature_LocPerfVal::Feature_LocPerfVal__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x49e0`
- `0x4aa0`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x4a60  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_LocPerfVal::Feature_LocPerfVal__private_featureState
0x4a65  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x4a6a  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_LocPerfVal::Feature_LocPerfVal__private_descriptor
0x4a6f  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x4a74  ret
```
