# Microsoft.Internal.Wil::wil_StagingConfig_QueryFeatureState

- ea: `0xa10`
- end: `0xa63`
- name: `Microsoft.Internal.Wil::wil_StagingConfig_QueryFeatureState`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa10`
- `0x128f0`
- `0x12c70`
- `0x12e40`
- `0x12e90`

## pseudocode

```c

```

## disassembly

```asm
0xa10  ldarg.1
0xa11  initobj  wil_FeatureState
0xa17  ldc.i4.0
0xa18  stloc.0
0xa19  ldc.i4   0xC8
0xa1e  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::AllocHGlobal(int32)
0xa23  stloc.1
0xa24  ldloca.s 2
0xa26  ldarg.0
0xa27  ldc.i4   0xC8
0xa2c  ldloc.1
0xa2d  ldc.i4.0
0xa2e  call     valuetype NTSTATUS Details::wil_details_StagingConfig_Load([out] valuetype wil_details_StagingConfig& config, valuetype wil_FeatureStore store, int32 bufferSize, native int buffer, bool forUpdate)
0xa33  brtrue.s loc_A58
0xa35  ldloca.s 2
0xa37  ldarg.1
0xa38  ldarg.2
0xa39  ldarg.3
0xa3a  call     bool Details::wil_details_StagingConfig_QueryFeatureState(valuetype wil_details_StagingConfig& config, [out] valuetype wil_FeatureState& state, unsigned int32 featureId, bool featureRequiresSessionChange)
0xa3f  stloc.0
0xa40  ldarg.s  4
0xa42  ldarg.s  4
0xa44  ldind.u1
0xa45  ldloca.s 2
0xa47  call     bool Details::wil_details_StagingConfig_AreAnyFeaturesConfigured(valuetype wil_details_StagingConfig& config)
0xa4c  or
0xa4d  stind.i1
0xa4e  leave.s  loc_A61
0xa50  ldloca.s 2
0xa52  call     void Details::wil_details_StagingConfig_Free(valuetype wil_details_StagingConfig& config)
0xa57  endfinally
0xa58  leave.s  loc_A61
0xa5a  ldloc.1
0xa5b  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeHGlobal(native int)
0xa60  endfinally
0xa61  ldloc.0
0xa62  ret
```
