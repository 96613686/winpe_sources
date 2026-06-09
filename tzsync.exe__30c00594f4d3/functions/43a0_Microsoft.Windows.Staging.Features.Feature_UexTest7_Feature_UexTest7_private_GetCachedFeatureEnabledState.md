# Microsoft.Windows.Staging.Features.Feature_UexTest7::Feature_UexTest7__private_GetCachedFeatureEnabledState

- ea: `0x43a0`
- end: `0x43b5`
- name: `Microsoft.Windows.Staging.Features.Feature_UexTest7::Feature_UexTest7__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4320`
- `0x43e0`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x43a0  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_UexTest7::Feature_UexTest7__private_featureState
0x43a5  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x43aa  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_UexTest7::Feature_UexTest7__private_descriptor
0x43af  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x43b4  ret
```
