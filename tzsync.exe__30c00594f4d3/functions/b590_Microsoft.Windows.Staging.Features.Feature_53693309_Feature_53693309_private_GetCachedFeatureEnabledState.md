# Microsoft.Windows.Staging.Features.Feature_53693309::Feature_53693309__private_GetCachedFeatureEnabledState

- ea: `0xb590`
- end: `0xb5a5`
- name: `Microsoft.Windows.Staging.Features.Feature_53693309::Feature_53693309__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb5d0`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0xb590  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_53693309::Feature_53693309__private_featureState
0xb595  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0xb59a  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_53693309::Feature_53693309__private_descriptor
0xb59f  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0xb5a4  ret
```
