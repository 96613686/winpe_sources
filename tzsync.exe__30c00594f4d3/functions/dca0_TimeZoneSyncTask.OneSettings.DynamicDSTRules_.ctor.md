# TimeZoneSyncTask.OneSettings.DynamicDSTRules::.ctor

- ea: `0xdca0`
- end: `0xdce1`
- name: `TimeZoneSyncTask.OneSettings.DynamicDSTRules::.ctor`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1200`
- `0xdc10`
- `0xdc30`
- `0xdc50`
- `0xdc70`
- `0xdc90`

## pseudocode

```c

```

## disassembly

```asm
0xdca0  ldarg.0
0xdca1  call     instance void [mscorlib]System.Object::.ctor()
0xdca6  call     bool Microsoft.Windows.Staging.Features.Feature_DSTOneSettingsSync::get_IsEnabled()
0xdcab  call     void [System]System.Diagnostics.Trace::Assert(bool)
0xdcb0  ldarg.0
0xdcb1  ldarg.1
0xdcb2  call     instance void TimeZoneSyncTask.OneSettings.DynamicDSTRules::set_zoneID(string value)
0xdcb7  ldarg.0
0xdcb8  ldarg.2
0xdcb9  call     instance void TimeZoneSyncTask.OneSettings.DynamicDSTRules::set_minYear(string value)
0xdcbe  ldarg.0
0xdcbf  ldarg.3
0xdcc0  call     instance void TimeZoneSyncTask.OneSettings.DynamicDSTRules::set_maxYear(string value)
0xdcc5  ldarg.0
0xdcc6  ldarg.s  4
0xdcc8  call     instance void TimeZoneSyncTask.OneSettings.DynamicDSTRules::set_tzVersion(unsigned int32 value)
0xdccd  ldarg.0
0xdcce  ldarg.s  5
0xdcd0  call     instance void TimeZoneSyncTask.OneSettings.DynamicDSTRules::set_tzi(valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData value)
0xdcd5  ldarg.0
0xdcd6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData>::.ctor()
0xdcdb  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype TimeZoneSyncTask.Data.RegistryTimeZoneData> TimeZoneSyncTask.OneSettings.DynamicDSTRules::DSTRules
0xdce0  ret
```
