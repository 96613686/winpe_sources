# TimeZoneSyncTask.Data.TimeOfDay::Equals_0

- ea: `0xf640`
- end: `0xf666`
- name: `TimeZoneSyncTask.Data.TimeOfDay::Equals_0`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0xf620`

## callees

- `0xf5e0`
- `0xf600`
- `0xf640`

## pseudocode

```c

```

## disassembly

```asm
0xf640  ldarg.0
0xf641  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.TimeOfDay::get_Duration()
0xf646  ldarga.s 1
0xf648  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.TimeOfDay::get_Duration()
0xf64d  call     bool [mscorlib]System.TimeSpan::op_Equality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xf652  brfalse.s loc_F664
0xf654  ldarg.0
0xf655  call     instance valuetype TimeZoneSyncTask.Data.TimeBase TimeZoneSyncTask.Data.TimeOfDay::get_Base()
0xf65a  ldarga.s 1
0xf65c  call     instance valuetype TimeZoneSyncTask.Data.TimeBase TimeZoneSyncTask.Data.TimeOfDay::get_Base()
0xf661  ceq
0xf663  ret
0xf664  ldc.i4.0
0xf665  ret
```
