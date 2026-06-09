# Microsoft.Windows.Staging.Features.Feature_BMB1::Feature_BMB1__private_GetCachedFeatureEnabledState

- ea: `0x5480`
- end: `0x5495`
- name: `Microsoft.Windows.Staging.Features.Feature_BMB1::Feature_BMB1__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5400`
- `0x54c0`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x5480  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_BMB1::Feature_BMB1__private_featureState
0x5485  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x548a  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_BMB1::Feature_BMB1__private_descriptor
0x548f  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x5494  ret
```
