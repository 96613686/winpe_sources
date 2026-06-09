# Microsoft.Internal.Wil::wil_RtlStagingConfig_QueryFeatureState

- ea: `0x920`
- end: `0xa06`
- name: `Microsoft.Internal.Wil::wil_RtlStagingConfig_QueryFeatureState`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8f0`

## callees

- `0x920`
- `0x13a30`
- `0x13bc0`
- `0x13c00`
- `0x13c40`
- `0x13c50`
- `0x13c60`
- `0x13c80`
- `0x13c90`
- `0x13e50`

## pseudocode

```c

```

## disassembly

```asm
0x920  ldc.i4.0
0x921  stloc.0
0x922  ldloca.s 1
0x924  initobj  RTL_FEATURE_CONFIGURATION
0x92a  ldloca.s 2
0x92c  initobj  RTL_FEATURE_CHANGE_STAMP
0x932  ldarg.2
0x933  brtrue.s loc_938
0x935  ldc.i4.1
0x936  br.s     loc_939
0x938  ldc.i4.0
0x939  stloc.3
0x93a  ldarg.1
0x93b  call     valuetype RTL_FEATURE_ID RTL_FEATURE_ID::op_Implicit(unsigned int32 featureId)
0x940  ldloc.3
0x941  ldloca.s 2
0x943  ldloca.s 1
0x945  call     valuetype NTSTATUS NtDll::RtlQueryFeatureConfiguration(valuetype RTL_FEATURE_ID FeatureId, valuetype RTL_FEATURE_CONFIGURATION_TYPE ConfiguationType, [out] valuetype RTL_FEATURE_CHANGE_STAMP& ChangeStamp, [out] valuetype RTL_FEATURE_CONFIGURATION& Configuration)
0x94a  stloc.s  4
0x94c  ldloc.s  4
0x94e  brtrue.s loc_9C4
0x950  ldarg.0
0x951  ldloca.s 5
0x953  initobj  wil_FeatureState
0x959  ldloca.s 5
0x95b  ldloca.s 1
0x95d  call     instance valuetype RTL_FEATURE_ENABLED_STATE RTL_FEATURE_CONFIGURATION::get_EnabledState()
0x962  stfld    valuetype wil_FeatureEnabledState wil_FeatureState::EnabledState
0x967  ldloca.s 5
0x969  ldloca.s 1
0x96b  call     instance valuetype RTL_FEATURE_VARIANT RTL_FEATURE_CONFIGURATION::get_Variant()
0x970  call     unsigned int8 RTL_FEATURE_VARIANT::op_Implicit(valuetype RTL_FEATURE_VARIANT variant)
0x975  stfld    unsigned int8 wil_FeatureState::Variant
0x97a  ldloca.s 5
0x97c  ldloc.1
0x97d  ldfld    valuetype RTL_FEATURE_VARIANT_PAYLOAD RTL_FEATURE_CONFIGURATION::VariantPayload
0x982  call     unsigned int32 RTL_FEATURE_VARIANT_PAYLOAD::op_Implicit(valuetype RTL_FEATURE_VARIANT_PAYLOAD variantPayload)
0x987  stfld    unsigned int32 wil_FeatureState::Payload
0x98c  ldloca.s 5
0x98e  ldloca.s 1
0x990  call     instance valuetype RTL_FEATURE_VARIANT_PAYLOAD_KIND RTL_FEATURE_CONFIGURATION::get_VariantPayloadKind()
0x995  stfld    valuetype wil_FeatureVariantPayloadKind wil_FeatureState::PayloadKind
0x99a  ldloca.s 5
0x99c  ldloca.s 1
0x99e  call     instance valuetype RTL_FEATURE_ENABLED_STATE_OPTIONS RTL_FEATURE_CONFIGURATION::get_IsWexpConfiguration()
0x9a3  ldc.i4.1
0x9a4  ceq
0x9a6  stfld    bool wil_FeatureState::IsWexpConfiguration
0x9ab  ldloca.s 5
0x9ad  ldloca.s 1
0x9af  call     instance bool RTL_FEATURE_CONFIGURATION::get_HasSubscriptions()
0x9b4  stfld    bool wil_FeatureState::HasNotification
0x9b9  ldloc.s  5
0x9bb  stobj    wil_FeatureState
0x9c0  ldc.i4.1
0x9c1  stloc.0
0x9c2  br.s     loc_9F6
0x9c4  ldloc.s  4
0x9c6  ldc.i4   0x117
0x9cb  bne.un.s loc_9EF
0x9cd  ldarg.0
0x9ce  ldloca.s 5
0x9d0  initobj  wil_FeatureState
0x9d6  ldloca.s 5
0x9d8  ldloca.s 1
0x9da  call     instance bool RTL_FEATURE_CONFIGURATION::get_HasSubscriptions()
0x9df  stfld    bool wil_FeatureState::HasNotification
0x9e4  ldloc.s  5
0x9e6  stobj    wil_FeatureState
0x9eb  ldc.i4.1
0x9ec  stloc.0
0x9ed  br.s     loc_9F6
0x9ef  ldarg.0
0x9f0  initobj  wil_FeatureState
0x9f6  ldarg.3
0x9f7  ldloc.s  4
0x9f9  ldc.i4   0x80000022
0x9fe  ceq
0xa00  ldc.i4.0
0xa01  ceq
0xa03  stind.i1
0xa04  ldloc.0
0xa05  ret
```
