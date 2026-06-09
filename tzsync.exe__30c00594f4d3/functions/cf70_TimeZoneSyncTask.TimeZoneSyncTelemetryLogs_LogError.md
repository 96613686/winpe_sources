# TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::LogError

- ea: `0xcf70`
- end: `0xcf90`
- name: `TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::LogError`
- size: `32`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0xcfb0`
- `0xcfd0`
- `0xcff0`

## callees

- `0xcf60`

## pseudocode

```c

```

## disassembly

```asm
0xcf70  call     class [mscorlib]System.Diagnostics.Tracing.EventSource TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::get_Log()
0xcf75  ldstr    aTzsyncError// "Tzsync Error"
0xcf7a  ldsfld   valuetype [mscorlib]System.Diagnostics.Tracing.EventSourceOptions TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::telemetryErrorOption
0xcf7f  ldarg.0
0xcf80  ldsfld   valuetype [mscorlib]System.Guid TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::sessionID
0xcf85  newobj   instance void class <>f__AnonymousType2`2<string, valuetype [mscorlib]System.Guid>::.ctor(var<u1>, !!T0)
0xcf8a  callvirt T0x2B00000D
0xcf8f  ret
```
