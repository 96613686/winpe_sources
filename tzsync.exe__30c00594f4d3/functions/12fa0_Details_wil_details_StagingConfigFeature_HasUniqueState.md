# Details::wil_details_StagingConfigFeature_HasUniqueState

- ea: `0x12fa0`
- end: `0x12fd4`
- name: `Details::wil_details_StagingConfigFeature_HasUniqueState`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x12c70`
- `0x12ee0`

## callees

- `0x12fa0`
- `0x14dd0`
- `0x14e50`
- `0x14e90`
- `0x14ed0`
- `0x14f90`

## pseudocode

```c

```

## disassembly

```asm
0x12fa0  ldarg.0
0x12fa1  ldfld    unsigned int32 wil_details_StagingConfigFeature::FeatureId
0x12fa6  brfalse.s loc_12FD2
0x12fa8  ldarg.0
0x12fa9  call     instance valuetype wil_FeatureEnabledState wil_details_StagingConfigFeature::get_ServiceState()
0x12fae  brtrue.s loc_12FD0
0x12fb0  ldarg.0
0x12fb1  call     instance valuetype wil_FeatureEnabledState wil_details_StagingConfigFeature::get_UserState()
0x12fb6  brtrue.s loc_12FD0
0x12fb8  ldarg.0
0x12fb9  call     instance valuetype wil_FeatureEnabledState wil_details_StagingConfigFeature::get_TestState()
0x12fbe  brtrue.s loc_12FD0
0x12fc0  ldarg.0
0x12fc1  call     instance unsigned int32 wil_details_StagingConfigFeature::get_Variant()
0x12fc6  brtrue.s loc_12FD0
0x12fc8  ldarg.0
0x12fc9  call     instance bool wil_details_StagingConfigFeature::get_IsWexpConfig()
0x12fce  brfalse.s loc_12FD2
0x12fd0  ldc.i4.1
0x12fd1  ret
0x12fd2  ldc.i4.0
0x12fd3  ret
```
