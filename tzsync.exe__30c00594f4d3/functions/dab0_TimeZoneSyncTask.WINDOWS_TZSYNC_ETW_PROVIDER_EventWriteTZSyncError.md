# TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteTZSyncError

- ea: `0xdab0`
- end: `0xdad1`
- name: `TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteTZSyncError`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xc470`

## callees

- `0xdab0`
- `0xdb00`

## pseudocode

```c

```

## disassembly

```asm
0xdab0  ldarg.0
0xdab1  ldfld    class TimeZoneSyncTask.EventProviderVersionTwo TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::m_provider
0xdab6  callvirt instance bool [System.Core]System.Diagnostics.Eventing.EventProvider::IsEnabled()
0xdabb  brtrue.s loc_DABF
0xdabd  ldc.i4.1
0xdabe  ret
0xdabf  ldarg.0
0xdac0  ldfld    class TimeZoneSyncTask.EventProviderVersionTwo TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::m_provider
0xdac5  ldarg.0
0xdac6  ldflda   valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::TZSyncError
0xdacb  callvirt instance bool TimeZoneSyncTask.EventProviderVersionTwo::TemplateEventDescriptor(valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor& eventDescriptor)
0xdad0  ret
```
