# TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceError

- ea: `0xcfd0`
- end: `0xcfe6`
- name: `TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceError`
- size: `22`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xcff0`
- `0xd2c0`
- `0x11550`
- `0x121c0`

## callees

- `0xcf70`
- `0xcfd0`

## pseudocode

```c

```

## disassembly

```asm
0xcfd0  ldarg.0
0xcfd1  ldarg.1
0xcfd2  call     void [System]System.Diagnostics.Trace::TraceError(string, object[])
0xcfd7  leave.s  loc_CFE5
0xcfd9  callvirt instance string [mscorlib]System.Exception::get_Message()
0xcfde  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::LogError(string error)
0xcfe3  leave.s  loc_CFE5
0xcfe5  ret
```
