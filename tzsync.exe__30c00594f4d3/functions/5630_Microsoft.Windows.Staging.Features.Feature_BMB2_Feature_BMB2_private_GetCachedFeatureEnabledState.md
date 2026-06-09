# Microsoft.Windows.Staging.Features.Feature_BMB2::Feature_BMB2__private_GetCachedFeatureEnabledState

- ea: `0x5630`
- end: `0x5645`
- name: `Microsoft.Windows.Staging.Features.Feature_BMB2::Feature_BMB2__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x55b0`
- `0x5670`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x5630  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_BMB2::Feature_BMB2__private_featureState
0x5635  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x563a  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_BMB2::Feature_BMB2__private_descriptor
0x563f  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x5644  ret
```
