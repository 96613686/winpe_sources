# TimeZoneSyncTask.OneSettings.OneSettingsWrapperDLL::.ctor

- ea: `0xe530`
- end: `0xe547`
- name: `TimeZoneSyncTask.OneSettings.OneSettingsWrapperDLL::.ctor`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0xcee0`

## callees

- `0x1200`
- `0xe550`

## pseudocode

```c

```

## disassembly

```asm
0xe530  ldarg.0
0xe531  call     instance void [mscorlib]System.Object::.ctor()
0xe536  call     bool Microsoft.Windows.Staging.Features.Feature_DSTOneSettingsSync::get_IsEnabled()
0xe53b  call     void [System]System.Diagnostics.Trace::Assert(bool)
0xe540  ldarg.0
0xe541  call     instance void TimeZoneSyncTask.OneSettings.OneSettingsWrapperDLL::ReadOneSetingsDataFromDLL()
0xe546  ret
```
