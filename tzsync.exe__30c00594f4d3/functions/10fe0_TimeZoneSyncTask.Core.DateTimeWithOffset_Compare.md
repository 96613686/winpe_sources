# TimeZoneSyncTask.Core.DateTimeWithOffset::Compare

- ea: `0x10fe0`
- end: `0x11019`
- name: `TimeZoneSyncTask.Core.DateTimeWithOffset::Compare`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x10b80`

## callees

- `0xec60`
- `0xec80`
- `0x10f90`
- `0x10fb0`
- `0x10fd0`
- `0x10fe0`

## pseudocode

```c

```

## disassembly

```asm
0x10fe0  ldarga.s 1
0x10fe2  call     instance valuetype TimeZoneSyncTask.Data.TimeBase TimeZoneSyncTask.Data.DateTimeEx::get_Base()
0x10fe7  stloc.1
0x10fe8  ldloc.1
0x10fe9  brfalse.s loc_10FF1
0x10feb  ldloc.1
0x10fec  ldc.i4.1
0x10fed  beq.s    loc_10FFA
0x10fef  br.s     loc_11003
0x10ff1  ldarg.0
0x10ff2  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Core.DateTimeWithOffset::ToLocalTime()
0x10ff7  stloc.0
0x10ff8  br.s     loc_1100A
0x10ffa  ldarg.0
0x10ffb  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Core.DateTimeWithOffset::ToLocalStandardTime()
0x11000  stloc.0
0x11001  br.s     loc_1100A
0x11003  ldarg.0
0x11004  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Core.DateTimeWithOffset::ToUtcTime()
0x11009  stloc.0
0x1100a  ldloca.s 0
0x1100c  ldarga.s 1
0x1100e  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.DateTimeEx::get_Time()
0x11013  call     instance int32 [mscorlib]System.DateTime::CompareTo(valuetype [mscorlib]System.DateTime)
0x11018  ret
```
