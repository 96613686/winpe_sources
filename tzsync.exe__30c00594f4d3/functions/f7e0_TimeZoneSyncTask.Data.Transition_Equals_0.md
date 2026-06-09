# TimeZoneSyncTask.Data.Transition::Equals_0

- ea: `0xf7e0`
- end: `0xf82a`
- name: `TimeZoneSyncTask.Data.Transition::Equals_0`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0xf7c0`

## callees

- `0xf720`
- `0xf740`
- `0xf760`
- `0xf780`
- `0xf7e0`

## pseudocode

```c

```

## disassembly

```asm
0xf7e0  ldarg.0
0xf7e1  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_UtcOffset()
0xf7e6  ldarg.1
0xf7e7  callvirt instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_UtcOffset()
0xf7ec  call     bool [mscorlib]System.TimeSpan::op_Equality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xf7f1  brfalse.s loc_F828
0xf7f3  ldarg.0
0xf7f4  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_LocalStandardOffset()
0xf7f9  ldarg.1
0xf7fa  callvirt instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_LocalStandardOffset()
0xf7ff  call     bool [mscorlib]System.TimeSpan::op_Equality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0xf804  brfalse.s loc_F828
0xf806  ldarg.0
0xf807  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0xf80c  ldarg.1
0xf80d  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0xf812  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xf817  brfalse.s loc_F828
0xf819  ldarg.0
0xf81a  call     instance valuetype TimeZoneSyncTask.Data.MidnightTransitionType TimeZoneSyncTask.Data.Transition::get_Type()
0xf81f  ldarg.1
0xf820  callvirt instance valuetype TimeZoneSyncTask.Data.MidnightTransitionType TimeZoneSyncTask.Data.Transition::get_Type()
0xf825  ceq
0xf827  ret
0xf828  ldc.i4.0
0xf829  ret
```
