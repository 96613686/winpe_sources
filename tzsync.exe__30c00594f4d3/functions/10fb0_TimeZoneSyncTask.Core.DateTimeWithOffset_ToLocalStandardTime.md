# TimeZoneSyncTask.Core.DateTimeWithOffset::ToLocalStandardTime

- ea: `0x10fb0`
- end: `0x10fc2`
- name: `TimeZoneSyncTask.Core.DateTimeWithOffset::ToLocalStandardTime`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x10fe0`

## callees

- `0x10f30`
- `0x10f50`

## pseudocode

```c

```

## disassembly

```asm
0x10fb0  ldarg.0
0x10fb1  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Core.DateTimeWithOffset::get_Time()
0x10fb6  ldarg.0
0x10fb7  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Core.DateTimeWithOffset::get_TsUtcOffset()
0x10fbc  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x10fc1  ret
```
