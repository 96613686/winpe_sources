# Details::wil_details_StagingConfig_EnumerateFeatures

- ea: `0x12ee0`
- end: `0x12f9d`
- name: `Details::wil_details_StagingConfig_EnumerateFeatures`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x12e40`

## callees

- `0x12ee0`
- `0x12fa0`
- `0x14880`
- `0x14d90`

## pseudocode

```c

```

## disassembly

```asm
0x12ee0  ldarg.0
0x12ee1  ldfld    native int wil_details_StagingConfig::Header
0x12ee6  call     T0x2B000041
0x12eeb  stloc.0
0x12eec  ldc.i4.0
0x12eed  stloc.1
0x12eee  br       loc_12F90
0x12ef3  ldarg.0
0x12ef4  ldfld    native int wil_details_StagingConfig::Features
0x12ef9  ldloc.1
0x12efa  call     T0x2B000042
0x12eff  mul.ovf
0x12f00  call     native int [mscorlib]System.IntPtr::op_Addition(native int, int32)
0x12f05  call     T0x2B000045
0x12f0a  stloc.2
0x12f0b  ldloca.s 2
0x12f0d  call     bool Details::wil_details_StagingConfigFeature_HasUniqueState(valuetype wil_details_StagingConfigFeature& feature)
0x12f12  brfalse.s loc_12F8C
0x12f14  ldloca.s 2
0x12f16  call     instance bool wil_details_StagingConfigFeature::get_ChangedInSession()
0x12f1b  brfalse.s loc_12F2C
0x12f1d  ldarg.1
0x12f1e  brfalse.s loc_12F8C
0x12f20  ldarg.1
0x12f21  ldloca.s 2
0x12f23  ldarg.2
0x12f24  callvirt instance bool __WIL_StagingConfigFeatureEnumeration::Invoke(valuetype wil_details_StagingConfigFeature& feature, object& context)
0x12f29  brfalse.s loc_12F8C
0x12f2b  ret
0x12f2c  ldc.i4.0
0x12f2d  stloc.3
0x12f2e  ldc.i4.0
0x12f2f  stloc.s  4
0x12f31  br.s     loc_12F82
0x12f33  ldarg.0
0x12f34  ldfld    native int wil_details_StagingConfig::Features
0x12f39  ldloc.s  4
0x12f3b  call     T0x2B000042
0x12f40  mul.ovf
0x12f41  call     native int [mscorlib]System.IntPtr::op_Addition(native int, int32)
0x12f46  call     T0x2B000045
0x12f4b  stloc.s  5
0x12f4d  ldloc.s  4
0x12f4f  ldloc.1
0x12f50  beq.s    loc_12F65
0x12f52  ldloc.2
0x12f53  ldfld    unsigned int32 wil_details_StagingConfigFeature::FeatureId
0x12f58  ldloc.s  5
0x12f5a  ldfld    unsigned int32 wil_details_StagingConfigFeature::FeatureId
0x12f5f  bne.un.s loc_12F65
0x12f61  ldc.i4.1
0x12f62  stloc.3
0x12f63  br.s     loc_12F8C
0x12f65  ldloc.3
0x12f66  brtrue.s loc_12F7C
0x12f68  ldarg.1
0x12f69  brtrue.s loc_12F6E
0x12f6b  ldc.i4.1
0x12f6c  br.s     loc_12F7A
0x12f6e  ldarg.1
0x12f6f  ldloca.s 2
0x12f71  ldarg.2
0x12f72  callvirt instance bool __WIL_StagingConfigFeatureEnumeration::Invoke(valuetype wil_details_StagingConfigFeature& feature, object& context)
0x12f77  ldc.i4.0
0x12f78  ceq
0x12f7a  brtrue.s loc_12F8C
0x12f7c  ldloc.s  4
0x12f7e  ldc.i4.1
0x12f7f  add
0x12f80  stloc.s  4
0x12f82  ldloc.s  4
0x12f84  ldloc.0
0x12f85  ldfld    unsigned int16 wil_details_StagingConfigHeader::FeatureCount
0x12f8a  blt.s    loc_12F33
0x12f8c  ldloc.1
0x12f8d  ldc.i4.1
0x12f8e  add
0x12f8f  stloc.1
0x12f90  ldloc.1
0x12f91  ldloc.0
0x12f92  ldfld    unsigned int16 wil_details_StagingConfigHeader::FeatureCount
0x12f97  blt      loc_12EF3
0x12f9c  ret
```
