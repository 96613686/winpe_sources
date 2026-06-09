# TimeZoneSyncTask.Core.WindowsProjectionTransform::ComputeLocalTime_0

- ea: `0x11ef0`
- end: `0x11f32`
- name: `TimeZoneSyncTask.Core.WindowsProjectionTransform::ComputeLocalTime_0`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x11f40`

## callees

- `0xf720`
- `0xf740`
- `0x14740`

## pseudocode

```c

```

## disassembly

```asm
0x11ef0  newobj   instance void <>c__DisplayClass3_0::.ctor()
0x11ef5  stloc.0
0x11ef6  ldloc.0
0x11ef7  ldarg.0
0x11ef8  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass3_0::dtCurrent
0x11efd  ldarg.1
0x11efe  ldloc.0
0x11eff  ldftn    instance bool <>c__DisplayClass3_0::<ComputeLocalTime>b__0(class TimeZoneSyncTask.Data.Transition t)
0x11f05  newobj   instance void class [mscorlib]System.Func`2<class TimeZoneSyncTask.Data.Transition, bool>::.ctor(object, native int)
0x11f0a  call     T0x2B000037
0x11f0f  call     T0x2B00002E
0x11f14  stloc.1
0x11f15  ldloc.0
0x11f16  ldfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass3_0::dtCurrent
0x11f1b  ldloc.1
0x11f1c  callvirt instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_UtcOffset()
0x11f21  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x11f26  ldloc.1
0x11f27  callvirt instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_LocalStandardOffset()
0x11f2c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x11f31  ret
```
