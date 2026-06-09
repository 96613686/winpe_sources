# TimeZoneSyncTask.Data.DateTimeEx::Equals_0

- ea: `0xecc0`
- end: `0xece6`
- name: `TimeZoneSyncTask.Data.DateTimeEx::Equals_0`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0xeca0`

## callees

- `0xec60`
- `0xec80`
- `0xecc0`

## pseudocode

```c

```

## disassembly

```asm
0xecc0  ldarg.0
0xecc1  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.DateTimeEx::get_Time()
0xecc6  ldarga.s 1
0xecc8  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.DateTimeEx::get_Time()
0xeccd  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xecd2  brfalse.s loc_ECE4
0xecd4  ldarg.0
0xecd5  call     instance valuetype TimeZoneSyncTask.Data.TimeBase TimeZoneSyncTask.Data.DateTimeEx::get_Base()
0xecda  ldarga.s 1
0xecdc  call     instance valuetype TimeZoneSyncTask.Data.TimeBase TimeZoneSyncTask.Data.DateTimeEx::get_Base()
0xece1  ceq
0xece3  ret
0xece4  ldc.i4.0
0xece5  ret
```
