# TimeZoneSyncTask.Core.DateTimeWithOffset::ToLocalTime

- ea: `0x10f90`
- end: `0x10fad`
- name: `TimeZoneSyncTask.Core.DateTimeWithOffset::ToLocalTime`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x10fe0`

## callees

- `0x10f30`
- `0x10f50`
- `0x10f70`

## pseudocode

```c

```

## disassembly

```asm
0x10f90  ldarg.0
0x10f91  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Core.DateTimeWithOffset::get_Time()
0x10f96  ldarg.0
0x10f97  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Core.DateTimeWithOffset::get_TsUtcOffset()
0x10f9c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x10fa1  ldarg.0
0x10fa2  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Core.DateTimeWithOffset::get_TsLocalStandardOffset()
0x10fa7  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x10fac  ret
```
