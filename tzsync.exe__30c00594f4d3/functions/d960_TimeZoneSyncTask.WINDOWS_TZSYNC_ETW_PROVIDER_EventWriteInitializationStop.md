# TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteInitializationStop

- ea: `0xd960`
- end: `0xd981`
- name: `TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteInitializationStop`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xc6e0`

## callees

- `0xd960`
- `0xdb00`

## pseudocode

```c

```

## disassembly

```asm
0xd960  ldarg.0
0xd961  ldfld    class TimeZoneSyncTask.EventProviderVersionTwo TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::m_provider
0xd966  callvirt instance bool [System.Core]System.Diagnostics.Eventing.EventProvider::IsEnabled()
0xd96b  brtrue.s loc_D96F
0xd96d  ldc.i4.1
0xd96e  ret
0xd96f  ldarg.0
0xd970  ldfld    class TimeZoneSyncTask.EventProviderVersionTwo TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::m_provider
0xd975  ldarg.0
0xd976  ldflda   valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::InitializationStop
0xd97b  callvirt instance bool TimeZoneSyncTask.EventProviderVersionTwo::TemplateEventDescriptor(valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor& eventDescriptor)
0xd980  ret
```
