# TimeZoneSyncTask.Core.WindowsProjectionTransform::ComputeNextTransition

- ea: `0x11f60`
- end: `0x11ff0`
- name: `TimeZoneSyncTask.Core.WindowsProjectionTransform::ComputeNextTransition`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x12080`

## callees

- `0x10320`
- `0x10340`
- `0x11f60`
- `0x14780`

## pseudocode

```c

```

## disassembly

```asm
0x11f60  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x11f65  stloc.0
0x11f66  ldloc.0
0x11f67  ldarg.0
0x11f68  stfld    valuetype [mscorlib]System.DateTime <>c__DisplayClass5_0::dtCurrent
0x11f6d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::.ctor()
0x11f72  dup
0x11f73  ldarga.s 1
0x11f75  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_StandardDate()
0x11f7a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::Add(var<u1>)
0x11f7f  dup
0x11f80  ldarga.s 1
0x11f82  call     instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> TimeZoneSyncTask.Data.WindowsProjection::get_DaylightDate()
0x11f87  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::Add(var<u1>)
0x11f8c  ldloc.0
0x11f8d  ldftn    instance bool <>c__DisplayClass5_0::<ComputeNextTransition>b__0(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> d)
0x11f93  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, bool>::.ctor(object, native int)
0x11f98  call     T0x2B000038
0x11f9d  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.DateTime> <>c::<>9__5_1
0x11fa2  dup
0x11fa3  brtrue.s loc_11FBC
0x11fa5  pop
0x11fa6  ldsfld   class <>c <>c::<>9
0x11fab  ldftn    instance valuetype [mscorlib]System.DateTime <>c::<ComputeNextTransition>b__5_1(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> d)
0x11fb1  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.DateTime>::.ctor(object, native int)
0x11fb6  dup
0x11fb7  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.DateTime> <>c::<>9__5_1
0x11fbc  call     T0x2B000039
0x11fc1  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.DateTime> <>c::<>9__5_2
0x11fc6  dup
0x11fc7  brtrue.s loc_11FE0
0x11fc9  pop
0x11fca  ldsfld   class <>c <>c::<>9
0x11fcf  ldftn    instance valuetype [mscorlib]System.DateTime <>c::<ComputeNextTransition>b__5_2(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> d)
0x11fd5  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.DateTime>::.ctor(object, native int)
0x11fda  dup
0x11fdb  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.DateTime> <>c::<>9__5_2
0x11fe0  call     T0x2B00003A
0x11fe5  call     T0x2B00003B
0x11fea  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x11fef  ret
```
