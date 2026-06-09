# Microsoft.Windows.Staging.Features.Feature_TestLoc03::Feature_TestLoc03__private_GetCachedFeatureEnabledState

- ea: `0x48b0`
- end: `0x48c5`
- name: `Microsoft.Windows.Staging.Features.Feature_TestLoc03::Feature_TestLoc03__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4830`
- `0x48f0`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x48b0  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_TestLoc03::Feature_TestLoc03__private_featureState
0x48b5  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x48ba  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_TestLoc03::Feature_TestLoc03__private_descriptor
0x48bf  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x48c4  ret
```
