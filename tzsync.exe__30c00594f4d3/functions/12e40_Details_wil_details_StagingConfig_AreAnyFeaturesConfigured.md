# Details::wil_details_StagingConfig_AreAnyFeaturesConfigured

- ea: `0x12e40`
- end: `0x12e8a`
- name: `Details::wil_details_StagingConfig_AreAnyFeaturesConfigured`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0xa10`

## callees

- `0x12e40`
- `0x12ee0`
- `0x14870`

## pseudocode

```c

```

## disassembly

```asm
0x12e40  ldc.i4.0
0x12e41  box      [mscorlib]System.Boolean
0x12e46  stloc.0
0x12e47  ldarg.0
0x12e48  ldsfld   class __WIL_StagingConfigFeatureEnumeration <>O::<0>__wil_details_StagingConfig_AreAnyFeaturesConfigured_Callback
0x12e4d  dup
0x12e4e  brtrue.s loc_12E63
0x12e50  pop
0x12e51  ldnull
0x12e52  ldftn    bool Details::wil_details_StagingConfig_AreAnyFeaturesConfigured_Callback(valuetype wil_details_StagingConfigFeature& feature, object& context)
0x12e58  newobj   instance void __WIL_StagingConfigFeatureEnumeration::.ctor(object object, native int method)
0x12e5d  dup
0x12e5e  stsfld   class __WIL_StagingConfigFeatureEnumeration <>O::<0>__wil_details_StagingConfig_AreAnyFeaturesConfigured_Callback
0x12e63  ldloca.s 0
0x12e65  call     void Details::wil_details_StagingConfig_EnumerateFeatures(valuetype wil_details_StagingConfig& config, class __WIL_StagingConfigFeatureEnumeration enumerationFunction, object& context)
0x12e6a  ldarg.0
0x12e6b  ldfld    native int wil_details_StagingConfig::Header
0x12e70  call     T0x2B000041
0x12e75  stloc.1
0x12e76  ldloc.0
0x12e77  unbox.any [mscorlib]System.Boolean
0x12e7c  brtrue.s loc_12E88
0x12e7e  ldloc.1
0x12e7f  ldfld    unsigned int16 wil_details_StagingConfigHeader::FeatureUsageTriggerCount
0x12e84  ldc.i4.0
0x12e85  cgt
0x12e87  ret
0x12e88  ldc.i4.1
0x12e89  ret
```
