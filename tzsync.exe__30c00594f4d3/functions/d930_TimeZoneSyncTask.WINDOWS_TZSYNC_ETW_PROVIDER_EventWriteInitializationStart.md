# TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteInitializationStart

- ea: `0xd930`
- end: `0xd951`
- name: `TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteInitializationStart`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xc470`

## callees

- `0xd930`
- `0xdb00`

## pseudocode

```c

```

## disassembly

```asm
0xd930  ldarg.0
0xd931  ldfld    class TimeZoneSyncTask.EventProviderVersionTwo TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::m_provider
0xd936  callvirt instance bool [System.Core]System.Diagnostics.Eventing.EventProvider::IsEnabled()
0xd93b  brtrue.s loc_D93F
0xd93d  ldc.i4.1
0xd93e  ret
0xd93f  ldarg.0
0xd940  ldfld    class TimeZoneSyncTask.EventProviderVersionTwo TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::m_provider
0xd945  ldarg.0
0xd946  ldflda   valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::InitializationStart
0xd94b  callvirt instance bool TimeZoneSyncTask.EventProviderVersionTwo::TemplateEventDescriptor(valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor& eventDescriptor)
0xd950  ret
```
