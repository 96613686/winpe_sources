# Details::wil_details_StagingConfig_QueryFeatureState

- ea: `0x12c70`
- end: `0x12e31`
- name: `Details::wil_details_StagingConfig_QueryFeatureState`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0xa10`

## callees

- `0x12c70`
- `0x12fa0`
- `0x14d90`
- `0x14dd0`
- `0x14e50`
- `0x14e70`
- `0x14e90`
- `0x14eb0`
- `0x14ed0`
- `0x14ef0`
- `0x14f90`
- `0x14fb0`
- `0x14fd0`
- `0x150d0`
- `0x15110`
- `0x15150`
- `0x15190`

## pseudocode

```c

```

## disassembly

```asm
0x12c70  ldarg.1
0x12c71  initobj  wil_FeatureState
0x12c77  ldarg.0
0x12c78  ldfld    native int wil_details_StagingConfig::Header
0x12c7d  call     T0x2B000041
0x12c82  stloc.0
0x12c83  ldc.i4.0
0x12c84  stloc.1
0x12c85  ldloca.s 2
0x12c87  initobj  wil_details_StagingConfigFeature
0x12c8d  ldc.i4.0
0x12c8e  stloc.s  5
0x12c90  br.s     loc_12CEC
0x12c92  ldarg.0
0x12c93  ldfld    native int wil_details_StagingConfig::Features
0x12c98  ldloc.s  5
0x12c9a  call     T0x2B000042
0x12c9f  mul.ovf
0x12ca0  call     native int [mscorlib]System.IntPtr::op_Addition(native int, int32)
0x12ca5  call     T0x2B000045
0x12caa  stloc.s  6
0x12cac  ldloc.s  6
0x12cae  ldfld    unsigned int32 wil_details_StagingConfigFeature::FeatureId
0x12cb3  ldarg.2
0x12cb4  bne.un.s loc_12CE6
0x12cb6  ldarg.3
0x12cb7  brfalse.s loc_12CD1
0x12cb9  ldarg.0
0x12cba  ldfld    bool wil_details_StagingConfig::ChangedInSession
0x12cbf  brfalse.s loc_12CD1
0x12cc1  ldloca.s 6
0x12cc3  call     instance bool wil_details_StagingConfigFeature::get_ChangedInSession()
0x12cc8  brtrue.s loc_12CE6
0x12cca  ldloc.s  6
0x12ccc  stloc.2
0x12ccd  ldc.i4.1
0x12cce  stloc.1
0x12ccf  br.s     loc_12CF6
0x12cd1  ldloca.s 6
0x12cd3  call     instance bool wil_details_StagingConfigFeature::get_ChangedInSession()
0x12cd8  brfalse.s loc_12CE1
0x12cda  ldloc.s  6
0x12cdc  stloc.2
0x12cdd  ldc.i4.1
0x12cde  stloc.1
0x12cdf  br.s     loc_12CF6
0x12ce1  ldloc.s  6
0x12ce3  stloc.2
0x12ce4  ldc.i4.1
0x12ce5  stloc.1
0x12ce6  ldloc.s  5
0x12ce8  ldc.i4.1
0x12ce9  add
0x12cea  stloc.s  5
0x12cec  ldloc.s  5
0x12cee  ldloc.0
0x12cef  ldfld    unsigned int16 wil_details_StagingConfigHeader::FeatureCount
0x12cf4  blt.s    loc_12C92
0x12cf6  ldc.i4.0
0x12cf7  stloc.3
0x12cf8  ldloc.1
0x12cf9  brfalse  loc_12DEA
0x12cfe  ldarg.3
0x12cff  brfalse.s loc_12D09
0x12d01  ldarg.0
0x12d02  ldfld    bool wil_details_StagingConfig::ChangedInSession
0x12d07  brtrue.s loc_12D11
0x12d09  ldloc.0
0x12d0a  ldfld    valuetype wil_details_StagingConfigHeaderProperties wil_details_StagingConfigHeader::SessionProperties
0x12d0f  br.s     loc_12D17
0x12d11  ldloc.0
0x12d12  ldfld    valuetype wil_details_StagingConfigHeaderProperties wil_details_StagingConfigHeader::Properties
0x12d17  stloc.s  7
0x12d19  ldloca.s 7
0x12d1b  call     instance bool wil_details_StagingConfigHeaderProperties::get_IgnoreTestState()
0x12d20  brfalse.s loc_12D2A
0x12d22  ldloca.s 2
0x12d24  ldc.i4.0
0x12d25  call     instance void wil_details_StagingConfigFeature::set_TestState(valuetype wil_FeatureEnabledState value)
0x12d2a  ldloca.s 7
0x12d2c  call     instance bool wil_details_StagingConfigHeaderProperties::get_IgnoreUserState()
0x12d31  brfalse.s loc_12D3B
0x12d33  ldloca.s 2
0x12d35  ldc.i4.0
0x12d36  call     instance void wil_details_StagingConfigFeature::set_UserState(valuetype wil_FeatureEnabledState value)
0x12d3b  ldloca.s 7
0x12d3d  call     instance bool wil_details_StagingConfigHeaderProperties::get_IgnoreServiceState()
0x12d42  brfalse.s loc_12D4C
0x12d44  ldloca.s 2
0x12d46  ldc.i4.0
0x12d47  call     instance void wil_details_StagingConfigFeature::set_ServiceState(valuetype wil_FeatureEnabledState value)
0x12d4c  ldloca.s 7
0x12d4e  call     instance bool wil_details_StagingConfigHeaderProperties::get_IgnoreVariants()
0x12d53  brfalse.s loc_12D65
0x12d55  ldloca.s 2
0x12d57  ldc.i4.0
0x12d58  call     instance void wil_details_StagingConfigFeature::set_Variant(unsigned int32 value)
0x12d5d  ldloca.s 2
0x12d5f  ldc.i4.0
0x12d60  stfld    unsigned int32 wil_details_StagingConfigFeature::Payload
0x12d65  ldloca.s 2
0x12d67  call     bool Details::wil_details_StagingConfigFeature_HasUniqueState(valuetype wil_details_StagingConfigFeature& feature)
0x12d6c  brfalse.s loc_12DEA
0x12d6e  ldarg.1
0x12d6f  ldloc.2
0x12d70  ldfld    unsigned int32 wil_details_StagingConfigFeature::Payload
0x12d75  stfld    unsigned int32 wil_FeatureState::Payload
0x12d7a  ldarg.1
0x12d7b  ldloca.s 2
0x12d7d  call     instance valuetype wil_FeatureVariantPayloadKind wil_details_StagingConfigFeature::get_PayloadKind()
0x12d82  stfld    valuetype wil_FeatureVariantPayloadKind wil_FeatureState::PayloadKind
0x12d87  ldarg.1
0x12d88  ldloca.s 2
0x12d8a  call     instance unsigned int32 wil_details_StagingConfigFeature::get_Variant()
0x12d8f  conv.u1
0x12d90  stfld    unsigned int8 wil_FeatureState::Variant
0x12d95  ldarg.1
0x12d96  ldloca.s 2
0x12d98  call     instance bool wil_details_StagingConfigFeature::get_IsWexpConfig()
0x12d9d  stfld    bool wil_FeatureState::IsWexpConfiguration
0x12da2  ldloca.s 2
0x12da4  call     instance valuetype wil_FeatureEnabledState wil_details_StagingConfigFeature::get_TestState()
0x12da9  brfalse.s loc_12DBA
0x12dab  ldarg.1
0x12dac  ldloca.s 2
0x12dae  call     instance valuetype wil_FeatureEnabledState wil_details_StagingConfigFeature::get_TestState()
0x12db3  stfld    valuetype wil_FeatureEnabledState wil_FeatureState::EnabledState
0x12db8  br.s     loc_12DE8
0x12dba  ldloca.s 2
0x12dbc  call     instance valuetype wil_FeatureEnabledState wil_details_StagingConfigFeature::get_UserState()
0x12dc1  brfalse.s loc_12DD2
0x12dc3  ldarg.1
0x12dc4  ldloca.s 2
0x12dc6  call     instance valuetype wil_FeatureEnabledState wil_details_StagingConfigFeature::get_UserState()
0x12dcb  stfld    valuetype wil_FeatureEnabledState wil_FeatureState::EnabledState
0x12dd0  br.s     loc_12DE8
0x12dd2  ldloca.s 2
0x12dd4  call     instance valuetype wil_FeatureEnabledState wil_details_StagingConfigFeature::get_ServiceState()
0x12dd9  brfalse.s loc_12DE8
0x12ddb  ldarg.1
0x12ddc  ldloca.s 2
0x12dde  call     instance valuetype wil_FeatureEnabledState wil_details_StagingConfigFeature::get_ServiceState()
0x12de3  stfld    valuetype wil_FeatureEnabledState wil_FeatureState::EnabledState
0x12de8  ldc.i4.1
0x12de9  stloc.3
0x12dea  ldc.i4.0
0x12deb  stloc.s  4
0x12ded  ldc.i4.0
0x12dee  stloc.s  8
0x12df0  br.s     loc_12E1D
0x12df2  ldarg.0
0x12df3  ldfld    native int wil_details_StagingConfig::Triggers
0x12df8  ldloc.s  8
0x12dfa  call     T0x2B000043
0x12dff  mul.ovf
0x12e00  call     native int [mscorlib]System.IntPtr::op_Addition(native int, int32)
0x12e05  call     T0x2B000046
0x12e0a  ldfld    unsigned int32 wil_details_StagingConfigUsageTrigger::FeatureId
0x12e0f  ldarg.2
0x12e10  bne.un.s loc_12E17
0x12e12  ldc.i4.1
0x12e13  stloc.s  4
0x12e15  br.s     loc_12E27
0x12e17  ldloc.s  8
0x12e19  ldc.i4.1
0x12e1a  add
0x12e1b  stloc.s  8
0x12e1d  ldloc.s  8
0x12e1f  ldloc.0
0x12e20  ldfld    unsigned int16 wil_details_StagingConfigHeader::FeatureCount
0x12e25  blt.s    loc_12DF2
0x12e27  ldarg.1
0x12e28  ldloc.s  4
0x12e2a  stfld    bool wil_FeatureState::HasNotification
0x12e2f  ldloc.3
0x12e30  ret
```
