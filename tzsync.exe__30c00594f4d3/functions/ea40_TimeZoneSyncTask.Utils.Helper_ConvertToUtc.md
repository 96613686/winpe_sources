# TimeZoneSyncTask.Utils.Helper::ConvertToUtc

- ea: `0xea40`
- end: `0xea7b`
- name: `TimeZoneSyncTask.Utils.Helper::ConvertToUtc`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x10970`
- `0x10b80`

## callees

- `0xea40`
- `0xec60`
- `0xec80`

## pseudocode

```c

```

## disassembly

```asm
0xea40  ldarga.s 0
0xea42  call     instance valuetype TimeZoneSyncTask.Data.TimeBase TimeZoneSyncTask.Data.DateTimeEx::get_Base()
0xea47  stloc.0
0xea48  ldloc.0
0xea49  brfalse.s loc_EA51
0xea4b  ldloc.0
0xea4c  ldc.i4.1
0xea4d  beq.s    loc_EA65
0xea4f  br.s     loc_EA73
0xea51  ldarga.s 0
0xea53  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.DateTimeEx::get_Time()
0xea58  ldarg.1
0xea59  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xea5e  ldarg.2
0xea5f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xea64  ret
0xea65  ldarga.s 0
0xea67  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.DateTimeEx::get_Time()
0xea6c  ldarg.1
0xea6d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0xea72  ret
0xea73  ldarga.s 0
0xea75  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.DateTimeEx::get_Time()
0xea7a  ret
```
