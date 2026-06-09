# TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::.ctor

- ea: `0xe5e0`
- end: `0xe5fc`
- name: `TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::.ctor`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0xe120`
- `0xe180`

## callees

- `0x1200`

## pseudocode

```c

```

## disassembly

```asm
0xe5e0  ldarg.0
0xe5e1  call     instance void [mscorlib]System.Object::.ctor()
0xe5e6  call     bool Microsoft.Windows.Staging.Features.Feature_DSTOneSettingsSync::get_IsEnabled()
0xe5eb  call     void [System]System.Diagnostics.Trace::Assert(bool)
0xe5f0  ldarg.0
0xe5f1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules>::.ctor()
0xe5f6  stfld    class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.OneSettings.DynamicDSTRules> TimeZoneSyncTask.OneSettings.TimeZoneDSTSettings::allDSTRules
0xe5fb  ret
```
