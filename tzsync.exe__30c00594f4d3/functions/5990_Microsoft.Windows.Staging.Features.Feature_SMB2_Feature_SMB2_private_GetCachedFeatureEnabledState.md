# Microsoft.Windows.Staging.Features.Feature_SMB2::Feature_SMB2__private_GetCachedFeatureEnabledState

- ea: `0x5990`
- end: `0x59a5`
- name: `Microsoft.Windows.Staging.Features.Feature_SMB2::Feature_SMB2__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x5910`
- `0x59d0`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x5990  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_SMB2::Feature_SMB2__private_featureState
0x5995  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x599a  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_SMB2::Feature_SMB2__private_descriptor
0x599f  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x59a4  ret
```
