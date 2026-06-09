# TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteTZSyncStart

- ea: `0xd8d0`
- end: `0xd8f1`
- name: `TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteTZSyncStart`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xc470`

## callees

- `0xd8d0`
- `0xdb00`

## pseudocode

```c

```

## disassembly

```asm
0xd8d0  ldarg.0
0xd8d1  ldfld    class TimeZoneSyncTask.EventProviderVersionTwo TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::m_provider
0xd8d6  callvirt instance bool [System.Core]System.Diagnostics.Eventing.EventProvider::IsEnabled()
0xd8db  brtrue.s loc_D8DF
0xd8dd  ldc.i4.1
0xd8de  ret
0xd8df  ldarg.0
0xd8e0  ldfld    class TimeZoneSyncTask.EventProviderVersionTwo TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::m_provider
0xd8e5  ldarg.0
0xd8e6  ldflda   valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::TZSyncStart
0xd8eb  callvirt instance bool TimeZoneSyncTask.EventProviderVersionTwo::TemplateEventDescriptor(valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor& eventDescriptor)
0xd8f0  ret
```
