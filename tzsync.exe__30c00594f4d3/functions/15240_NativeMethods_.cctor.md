# NativeMethods::.cctor

- ea: `0x15240`
- end: `0x152a1`
- name: `NativeMethods::.cctor`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x15470`
- `0x154c0`
- `0x15510`

## string_xrefs

- `0x15240`: `NtDll`
- `0x15260`: `NtDll`
- `0x15280`: `NtDll`
- `0x15245`: `RtlQueryAllFeatureConfigurations`
- `0x15265`: `RtlQueryFeatureConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x15240  ldstr    aNtdll// "NtDll"
0x15245  ldstr    aRtlqueryallfea// "RtlQueryAllFeatureConfigurations"
0x1524a  ldnull
0x1524b  ldftn    valuetype NTSTATUS NativeMethods::RtlQueryAllFeatureConfigurationsFallback(valuetype RTL_FEATURE_CONFIGURATION_TYPE _, [out] valuetype RTL_FEATURE_CHANGE_STAMP& ChangeStamp, native int __, native unsigned int& ___)
0x15251  newobj   instance void RtlQueryAllFeatureConfigurationsFn::.ctor(object object, native int method)
0x15256  call     T0x2B00004C
0x1525b  stsfld   class RtlQueryAllFeatureConfigurationsFn NativeMethods::RtlQueryAllFeatureConfigurationsFnValue
0x15260  ldstr    aNtdll// "NtDll"
0x15265  ldstr    aRtlqueryfeatur// "RtlQueryFeatureConfiguration"
0x1526a  ldnull
0x1526b  ldftn    valuetype NTSTATUS NativeMethods::RtlQueryFeatureConfigurationFallback(valuetype RTL_FEATURE_ID _, valuetype RTL_FEATURE_CONFIGURATION_TYPE __, [out] valuetype RTL_FEATURE_CHANGE_STAMP& ChangeStamp, [out] valuetype RTL_FEATURE_CONFIGURATION& Configuration)
0x15271  newobj   instance void RtlQueryFeatureConfigurationFn::.ctor(object object, native int method)
0x15276  call     T0x2B00004D
0x1527b  stsfld   class RtlQueryFeatureConfigurationFn NativeMethods::RtlQueryFeatureConfigurationFnValue
0x15280  ldstr    aNtdll// "NtDll"
0x15285  ldstr    aNtquerywnfstat// "NtQueryWnfStateData"
0x1528a  ldnull
0x1528b  ldftn    valuetype NTSTATUS NativeMethods::NtQueryWnfStateDataFallback(valuetype WIL_WNF_STATE_NAME& StateName, native int TypeId, native int ExplicitScope, int32& ChangeStamp, native int Buffer, int32& BufferSize)
0x15291  newobj   instance void NtQueryWnfStateDataFn::.ctor(object object, native int method)
0x15296  call     T0x2B00004E
0x1529b  stsfld   class NtQueryWnfStateDataFn NativeMethods::NtQueryWnfStateDataFnValue
0x152a0  ret
```
