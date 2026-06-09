# Microsoft.Windows.Staging.Features.Feature_TestLoc02::Feature_TestLoc02__private_GetCachedFeatureEnabledState

- ea: `0x4700`
- end: `0x4715`
- name: `Microsoft.Windows.Staging.Features.Feature_TestLoc02::Feature_TestLoc02__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4680`
- `0x4740`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x4700  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_TestLoc02::Feature_TestLoc02__private_featureState
0x4705  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x470a  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_TestLoc02::Feature_TestLoc02__private_descriptor
0x470f  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x4714  ret
```
