# TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::WriteAndTrace

- ea: `0xcff0`
- end: `0xd043`
- name: `TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::WriteAndTrace`
- size: `83`
- prototype: ``
- caller_count: `5`
- callee_count: `6`
- tags: `service_task`

## callers

- `0xc470`
- `0xc620`
- `0xc6e0`
- `0xce40`
- `0xcee0`

## callees

- `0x1050`
- `0xcf70`
- `0xcf90`
- `0xcfb0`
- `0xcfd0`
- `0xcff0`

## pseudocode

```c

```

## disassembly

```asm
0xcff0  ldarg.0
0xcff1  brfalse.s loc_CFF7
0xcff3  ldarg.0
0xcff4  ldc.i4.1
0xcff5  beq.s    loc_D01D
0xcff7  call     bool Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::get_IsEnabled()
0xcffc  brfalse.s loc_D010
0xcffe  ldarg.1
0xcfff  call     T0x2B00000F
0xd004  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo(string format, object[] args)
0xd009  ldarg.1
0xd00a  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::LogInfo(string info)
0xd00f  ret
0xd010  ldarg.1
0xd011  call     void [System]System.Diagnostics.Trace::TraceInformation(string)
0xd016  ldarg.1
0xd017  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::LogInfo(string info)
0xd01c  ret
0xd01d  call     bool Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::get_IsEnabled()
0xd022  brfalse.s loc_D036
0xd024  ldarg.1
0xd025  call     T0x2B00000F
0xd02a  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceError(string format, object[] args)
0xd02f  ldarg.1
0xd030  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::LogError(string error)
0xd035  ret
0xd036  ldarg.1
0xd037  call     void [System]System.Diagnostics.Trace::TraceError(string)
0xd03c  ldarg.1
0xd03d  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::LogError(string error)
0xd042  ret
```
