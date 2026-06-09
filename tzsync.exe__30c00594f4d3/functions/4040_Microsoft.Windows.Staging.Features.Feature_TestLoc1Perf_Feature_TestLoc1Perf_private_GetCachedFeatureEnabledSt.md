# Microsoft.Windows.Staging.Features.Feature_TestLoc1Perf::Feature_TestLoc1Perf__private_GetCachedFeatureEnabledState

- ea: `0x4040`
- end: `0x4055`
- name: `Microsoft.Windows.Staging.Features.Feature_TestLoc1Perf::Feature_TestLoc1Perf__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3fc0`
- `0x4080`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x4040  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_TestLoc1Perf::Feature_TestLoc1Perf__private_featureState
0x4045  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x404a  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_TestLoc1Perf::Feature_TestLoc1Perf__private_descriptor
0x404f  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x4054  ret
```
