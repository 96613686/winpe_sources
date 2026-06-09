# TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteConversionStart

- ea: `0xd990`
- end: `0xd9b1`
- name: `TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteConversionStart`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xc6e0`

## callees

- `0xd990`
- `0xdb00`

## pseudocode

```c

```

## disassembly

```asm
0xd990  ldarg.0
0xd991  ldfld    class TimeZoneSyncTask.EventProviderVersionTwo TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::m_provider
0xd996  callvirt instance bool [System.Core]System.Diagnostics.Eventing.EventProvider::IsEnabled()
0xd99b  brtrue.s loc_D99F
0xd99d  ldc.i4.1
0xd99e  ret
0xd99f  ldarg.0
0xd9a0  ldfld    class TimeZoneSyncTask.EventProviderVersionTwo TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::m_provider
0xd9a5  ldarg.0
0xd9a6  ldflda   valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::ConversionStart
0xd9ab  callvirt instance bool TimeZoneSyncTask.EventProviderVersionTwo::TemplateEventDescriptor(valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor& eventDescriptor)
0xd9b0  ret
```
