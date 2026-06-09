# TimeZoneSyncTask.Core.WindowsProjectionTransform::ComputeNextTransition_0

- ea: `0x11ff0`
- end: `0x12072`
- name: `TimeZoneSyncTask.Core.WindowsProjectionTransform::ComputeNextTransition_0`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x12080`

## callees

- `0x10510`
- `0x10530`
- `0x11ff0`
- `0x147d0`

## pseudocode

```c

```

## disassembly

```asm
0x11ff0  newobj   instance void <>c__DisplayClass6_0::.ctor()
0x11ff5  stloc.0
0x11ff6  ldloc.0
0x11ff7  ldarg.0
0x11ff8  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass6_0::dtCurrent
0x11ffd  ldarg.1
0x11ffe  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetStandardDates()
0x12003  ldarg.1
0x12004  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetDaylightDates()
0x12009  call     T0x2B00003C
0x1200e  ldloc.0
0x1200f  ldftn    instance bool <>c__DisplayClass6_0::<ComputeNextTransition>b__0(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> dt)
0x12015  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, bool>::.ctor(object, native int)
0x1201a  call     T0x2B000038
0x1201f  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.DateTime> <>c::<>9__6_1
0x12024  dup
0x12025  brtrue.s loc_1203E
0x12027  pop
0x12028  ldsfld   class <>c <>c::<>9
0x1202d  ldftn    instance valuetype [mscorlib]System.DateTime <>c::<ComputeNextTransition>b__6_1(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> dt)
0x12033  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.DateTime>::.ctor(object, native int)
0x12038  dup
0x12039  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.DateTime> <>c::<>9__6_1
0x1203e  call     T0x2B000039
0x12043  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.DateTime> <>c::<>9__6_2
0x12048  dup
0x12049  brtrue.s loc_12062
0x1204b  pop
0x1204c  ldsfld   class <>c <>c::<>9
0x12051  ldftn    instance valuetype [mscorlib]System.DateTime <>c::<ComputeNextTransition>b__6_2(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> dt)
0x12057  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.DateTime>::.ctor(object, native int)
0x1205c  dup
0x1205d  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.DateTime> <>c::<>9__6_2
0x12062  call     T0x2B00003A
0x12067  call     T0x2B00003B
0x1206c  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x12071  ret
```
