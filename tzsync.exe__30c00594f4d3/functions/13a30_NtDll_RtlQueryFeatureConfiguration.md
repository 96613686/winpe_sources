# NtDll::RtlQueryFeatureConfiguration

- ea: `0x13a30`
- end: `0x13a3f`
- name: `NtDll::RtlQueryFeatureConfiguration`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x920`

## callees

- `0x152b0`
- `0x15480`

## pseudocode

```c

```

## disassembly

```asm
0x13a30  call     class RtlQueryFeatureConfigurationFn NativeMethods::get_RtlQueryFeatureConfiguration()
0x13a35  ldarg.0
0x13a36  ldarg.1
0x13a37  ldarg.2
0x13a38  ldarg.3
0x13a39  callvirt instance valuetype NTSTATUS RtlQueryFeatureConfigurationFn::Invoke(valuetype RTL_FEATURE_ID FeatureId, valuetype RTL_FEATURE_CONFIGURATION_TYPE ConfiguationType, [out] valuetype RTL_FEATURE_CHANGE_STAMP& ChangeStamp, [out] valuetype RTL_FEATURE_CONFIGURATION& Configuration)
0x13a3e  ret
```
