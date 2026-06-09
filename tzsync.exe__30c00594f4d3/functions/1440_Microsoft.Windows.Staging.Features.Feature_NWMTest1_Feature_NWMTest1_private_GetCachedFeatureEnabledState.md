# Microsoft.Windows.Staging.Features.Feature_NWMTest1::Feature_NWMTest1__private_GetCachedFeatureEnabledState

- ea: `0x1440`
- end: `0x1455`
- name: `Microsoft.Windows.Staging.Features.Feature_NWMTest1::Feature_NWMTest1__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x13c0`
- `0x1480`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x1440  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_NWMTest1::Feature_NWMTest1__private_featureState
0x1445  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x144a  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_NWMTest1::Feature_NWMTest1__private_descriptor
0x144f  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x1454  ret
```
