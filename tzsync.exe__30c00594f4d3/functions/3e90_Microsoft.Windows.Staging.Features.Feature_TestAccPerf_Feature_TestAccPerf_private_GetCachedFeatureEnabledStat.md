# Microsoft.Windows.Staging.Features.Feature_TestAccPerf::Feature_TestAccPerf__private_GetCachedFeatureEnabledState

- ea: `0x3e90`
- end: `0x3ea5`
- name: `Microsoft.Windows.Staging.Features.Feature_TestAccPerf::Feature_TestAccPerf__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3e10`
- `0x3ed0`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x3e90  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_TestAccPerf::Feature_TestAccPerf__private_featureState
0x3e95  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x3e9a  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_TestAccPerf::Feature_TestAccPerf__private_descriptor
0x3e9f  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x3ea4  ret
```
