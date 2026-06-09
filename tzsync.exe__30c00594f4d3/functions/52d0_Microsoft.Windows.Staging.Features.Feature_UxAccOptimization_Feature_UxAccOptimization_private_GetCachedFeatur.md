# Microsoft.Windows.Staging.Features.Feature_UxAccOptimization::Feature_UxAccOptimization__private_GetCachedFeatureEnabledState

- ea: `0x52d0`
- end: `0x52e5`
- name: `Microsoft.Windows.Staging.Features.Feature_UxAccOptimization::Feature_UxAccOptimization__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5250`
- `0x5310`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x52d0  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_UxAccOptimization::Feature_UxAccOptimization__private_featureState
0x52d5  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x52da  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_UxAccOptimization::Feature_UxAccOptimization__private_descriptor
0x52df  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x52e4  ret
```
