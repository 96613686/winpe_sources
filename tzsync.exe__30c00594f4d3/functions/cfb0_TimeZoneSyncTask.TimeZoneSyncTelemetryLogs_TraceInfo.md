# TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo

- ea: `0xcfb0`
- end: `0xcfc6`
- name: `TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo`
- size: `22`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `service_task`

## callers

- `0xc6e0`
- `0xcff0`
- `0xd1e0`
- `0x11030`
- `0x11190`
- `0x112f0`
- `0x11550`

## callees

- `0xcf70`
- `0xcfb0`

## pseudocode

```c

```

## disassembly

```asm
0xcfb0  ldarg.0
0xcfb1  ldarg.1
0xcfb2  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0xcfb7  leave.s  loc_CFC5
0xcfb9  callvirt instance string [mscorlib]System.Exception::get_Message()
0xcfbe  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::LogError(string error)
0xcfc3  leave.s  loc_CFC5
0xcfc5  ret
```
