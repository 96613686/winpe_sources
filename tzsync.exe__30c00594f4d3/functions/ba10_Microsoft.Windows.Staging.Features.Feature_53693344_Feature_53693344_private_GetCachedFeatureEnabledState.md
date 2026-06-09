# Microsoft.Windows.Staging.Features.Feature_53693344::Feature_53693344__private_GetCachedFeatureEnabledState

- ea: `0xba10`
- end: `0xba25`
- name: `Microsoft.Windows.Staging.Features.Feature_53693344::Feature_53693344__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xba50`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0xba10  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_53693344::Feature_53693344__private_featureState
0xba15  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0xba1a  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_53693344::Feature_53693344__private_descriptor
0xba1f  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0xba24  ret
```
