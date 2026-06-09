# TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteConversionStop

- ea: `0xd9c0`
- end: `0xd9e1`
- name: `TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteConversionStop`
- size: `33`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xc6e0`

## callees

- `0xd9c0`
- `0xdb00`

## pseudocode

```c

```

## disassembly

```asm
0xd9c0  ldarg.0
0xd9c1  ldfld    class TimeZoneSyncTask.EventProviderVersionTwo TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::m_provider
0xd9c6  callvirt instance bool [System.Core]System.Diagnostics.Eventing.EventProvider::IsEnabled()
0xd9cb  brtrue.s loc_D9CF
0xd9cd  ldc.i4.1
0xd9ce  ret
0xd9cf  ldarg.0
0xd9d0  ldfld    class TimeZoneSyncTask.EventProviderVersionTwo TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::m_provider
0xd9d5  ldarg.0
0xd9d6  ldflda   valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::ConversionStop
0xd9db  callvirt instance bool TimeZoneSyncTask.EventProviderVersionTwo::TemplateEventDescriptor(valuetype [System.Core]System.Diagnostics.Eventing.EventDescriptor& eventDescriptor)
0xd9e0  ret
```
