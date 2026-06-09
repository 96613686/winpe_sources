# TimeZoneSyncTask.TimeZoneSync::Require

- ea: `0xce30`
- end: `0xce3d`
- name: `TimeZoneSyncTask.TimeZoneSync::Require`
- size: `13`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: `service_task`

## callers

- `0xe8d0`
- `0xe900`
- `0xe940`
- `0xeab0`
- `0xeaf0`
- `0xec20`
- `0xed40`
- `0xfa00`
- `0xfe80`
- `0x10970`
- `0x11790`
- `0x120f0`
- `0x121c0`
- `0x123f0`
- `0x12530`

## callees

- `0xce40`

## pseudocode

```c

```

## disassembly

```asm
0xce30  ldarg.0
0xce31  ldstr    aData// "Data"
0xce36  ldarg.1
0xce37  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string exceptiontype, string msg)
0xce3c  ret
```
