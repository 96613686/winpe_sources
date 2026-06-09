# Microsoft.Windows.Staging.Features.Feature_SMB1::Feature_SMB1__private_GetCachedFeatureEnabledState

- ea: `0x57e0`
- end: `0x57f5`
- name: `Microsoft.Windows.Staging.Features.Feature_SMB1::Feature_SMB1__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5760`
- `0x5820`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x57e0  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_SMB1::Feature_SMB1__private_featureState
0x57e5  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x57ea  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_SMB1::Feature_SMB1__private_descriptor
0x57ef  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x57f4  ret
```
