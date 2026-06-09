# Microsoft.Windows.Staging.Features.Feature_DSTOneSettingsSync::Feature_DSTOneSettingsSync__private_GetCachedFeatureEnabledState

- ea: `0x1290`
- end: `0x12a5`
- name: `Microsoft.Windows.Staging.Features.Feature_DSTOneSettingsSync::Feature_DSTOneSettingsSync__private_GetCachedFeatureEnabledState`
- size: `21`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1210`
- `0x12d0`

## callees

- `0x12890`

## pseudocode

```c

```

## disassembly

```asm
0x1290  ldsfld   class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache> Microsoft.Windows.Staging.Features.Feature_DSTOneSettingsSync::Feature_DSTOneSettingsSync__private_featureState
0x1295  ldflda   var<u1> class Microsoft.Internal.PInvoke.Util.Box`1<valuetype wil_details_FeatureStateCache>::Value
0x129a  ldsflda  valuetype wil_details_FeatureDescriptor Microsoft.Windows.Staging.Features.Feature_DSTOneSettingsSync::Feature_DSTOneSettingsSync__private_descriptor
0x129f  call     valuetype wil_details_FeatureStateCache Details::wil_details_FeatureStateCache_GetCachedFeatureEnabledState(valuetype wil_details_FeatureStateCache& featureState, valuetype wil_details_FeatureDescriptor& descriptor)
0x12a4  ret
```
