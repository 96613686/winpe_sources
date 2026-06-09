# Microsoft.Windows.Staging.Features.Feature_Ten2Loc::Feature_Ten2Loc__private_GetCachedFeatureEnabledState

- ea: `0x41f0`
- end: `0x4205`
- name: `Microsoft.Windows.Staging.Features.Feature_Ten2Loc::Feature_Ten2Loc__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4170`
- `0x4230`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x41f0  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_Ten2Loc::Feature_Ten2Loc__private_featureState
0x41f5  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x41fa  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_Ten2Loc::Feature_Ten2Loc__private_descriptor
0x41ff  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x4204  ret
```
