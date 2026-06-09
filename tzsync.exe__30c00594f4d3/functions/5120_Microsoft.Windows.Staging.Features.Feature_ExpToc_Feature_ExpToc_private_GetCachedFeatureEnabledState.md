# Microsoft.Windows.Staging.Features.Feature_ExpToc::Feature_ExpToc__private_GetCachedFeatureEnabledState

- ea: `0x5120`
- end: `0x5135`
- name: `Microsoft.Windows.Staging.Features.Feature_ExpToc::Feature_ExpToc__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x50a0`
- `0x5160`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x5120  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_ExpToc::Feature_ExpToc__private_featureState
0x5125  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x512a  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_ExpToc::Feature_ExpToc__private_descriptor
0x512f  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x5134  ret
```
