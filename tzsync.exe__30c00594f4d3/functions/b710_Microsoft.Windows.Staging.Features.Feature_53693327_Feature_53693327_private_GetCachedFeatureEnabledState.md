# Microsoft.Windows.Staging.Features.Feature_53693327::Feature_53693327__private_GetCachedFeatureEnabledState

- ea: `0xb710`
- end: `0xb725`
- name: `Microsoft.Windows.Staging.Features.Feature_53693327::Feature_53693327__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb750`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0xb710  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_53693327::Feature_53693327__private_featureState
0xb715  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0xb71a  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_53693327::Feature_53693327__private_descriptor
0xb71f  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0xb724  ret
```
