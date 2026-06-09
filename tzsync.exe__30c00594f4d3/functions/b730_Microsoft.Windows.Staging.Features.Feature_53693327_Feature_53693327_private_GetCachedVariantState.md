# Microsoft.Windows.Staging.Features.Feature_53693327::Feature_53693327__private_GetCachedVariantState

- ea: `0xb730`
- end: `0xb745`
- name: `Microsoft.Windows.Staging.Features.Feature_53693327::Feature_53693327__private_GetCachedVariantState`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb770`

## callees

- `0x128c0`

## pseudocode

```c

```

## disassembly

```asm
0xb730  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_53693327::Feature_53693327__private_featureState
0xb735  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0xb73a  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_53693327::Feature_53693327__private_descriptor
0xb73f  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedVariantState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0xb744  ret
```
