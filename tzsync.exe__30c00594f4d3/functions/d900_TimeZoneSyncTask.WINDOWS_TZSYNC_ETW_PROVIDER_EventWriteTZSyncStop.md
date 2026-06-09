# TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteTZSyncStop

- ea: `0xd900`
- end: `0xd921`
- name: `TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteTZSyncStop`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xc470`

## callees

- `0xd900`
- `0xdb00`

## pseudocode

```c

```

## disassembly

```asm
0xd900  ldarg.0
0xd901  ldfld    class TimeZoneSyncTask.EventProviderVersionTwo TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::m_provider
0xd906  callvirt instance bool [System.Core]System.Diagnostics.Eventing.EventProvider::IsEnabled()
0xd90b  brtrue.s loc_D90F
0xd90d  ldc.i4.1
0xd90e  ret
0xd90f  ldarg.0
0xd910  ldfld    class TimeZoneSyncTask.EventProviderVersionTwo TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::m_provider
0xd915  ldarg.0
0xd916  ldflda   valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::TZSyncStop
0xd91b  callvirt instance bool TimeZoneSyncTask.EventProviderVersionTwo::TemplateEventDescriptor(valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor& eventDescriptor)
0xd920  ret
```
