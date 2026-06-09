# Microsoft.Windows.Staging.Features.Feature_ValAccTest::Feature_ValAccTest__private_GetCachedFeatureEnabledState

- ea: `0x3ce0`
- end: `0x3cf5`
- name: `Microsoft.Windows.Staging.Features.Feature_ValAccTest::Feature_ValAccTest__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3c60`
- `0x3d20`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x3ce0  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_ValAccTest::Feature_ValAccTest__private_featureState
0x3ce5  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x3cea  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_ValAccTest::Feature_ValAccTest__private_descriptor
0x3cef  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x3cf4  ret
```
