# Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::Feature_FixBug2886555_TryTraceCatch__private_GetCachedFeatureEnabledState

- ea: `0x10e0`
- end: `0x10f5`
- name: `Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::Feature_FixBug2886555_TryTraceCatch__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1060`
- `0x1120`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x10e0  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::Feature_FixBug2886555_TryTraceCatch__private_featureState
0x10e5  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x10ea  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::Feature_FixBug2886555_TryTraceCatch__private_descriptor
0x10ef  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x10f4  ret
```
