# TimeZoneSyncTask.Core.WindowsProjectionTransform::AmountOfTimeAccurate

- ea: `0x11c70`
- end: `0x11dc0`
- name: `TimeZoneSyncTask.Core.WindowsProjectionTransform::AmountOfTimeAccurate`
- size: `336`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x146d0`

## callees

- `0xea80`
- `0xf760`
- `0x11c70`
- `0x11f40`
- `0x14700`

## pseudocode

```c

```

## disassembly

```asm
0x11c70  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x11c75  stloc.0
0x11c76  ldloc.0
0x11c77  ldarg.0
0x11c78  stfld    int32 <>c__DisplayClass1_0::year
0x11c7d  ldloca.s 1
0x11c7f  ldloc.0
0x11c80  ldfld    int32 <>c__DisplayClass1_0::year
0x11c85  ldc.i4.1
0x11c86  ldc.i4.1
0x11c87  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0x11c8c  ldloca.s 2
0x11c8e  ldloc.0
0x11c8f  ldfld    int32 <>c__DisplayClass1_0::year
0x11c94  ldc.i4.1
0x11c95  add
0x11c96  ldc.i4.1
0x11c97  ldc.i4.1
0x11c98  call     instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0x11c9d  newobj   instance void class [System]System.Collections.Generic.SortedSet`1<valuetype [mscorlib]System.DateTime>::.ctor()
0x11ca2  stloc.3
0x11ca3  ldloc.3
0x11ca4  ldloc.1
0x11ca5  callvirt instance bool class [System]System.Collections.Generic.SortedSet`1<valuetype [mscorlib]System.DateTime>::Add(var<u1>)
0x11caa  pop
0x11cab  ldloc.3
0x11cac  ldloc.2
0x11cad  callvirt instance bool class [System]System.Collections.Generic.SortedSet`1<valuetype [mscorlib]System.DateTime>::Add(var<u1>)
0x11cb2  pop
0x11cb3  ldarg.2
0x11cb4  ldloc.0
0x11cb5  ldfld    class [mscorlib]System.Func`2<class TimeZoneSyncTask.Data.Transition, bool> <>c__DisplayClass1_0::<>9__0
0x11cba  dup
0x11cbb  brtrue.s loc_11CD5
0x11cbd  pop
0x11cbe  ldloc.0
0x11cbf  ldloc.0
0x11cc0  ldftn    instance bool <>c__DisplayClass1_0::<AmountOfTimeAccurate>b__0(class TimeZoneSyncTask.Data.Transition t)
0x11cc6  newobj   instance void class [mscorlib]System.Func`2<class TimeZoneSyncTask.Data.Transition, bool>::.ctor(object, native int)
0x11ccb  dup
0x11ccc  stloc.s  7
0x11cce  stfld    class [mscorlib]System.Func`2<class TimeZoneSyncTask.Data.Transition, bool> <>c__DisplayClass1_0::<>9__0
0x11cd3  ldloc.s  7
0x11cd5  call     T0x2B00002B
0x11cda  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class TimeZoneSyncTask.Data.Transition>::GetEnumerator()
0x11cdf  stloc.s  6
0x11ce1  br.s     loc_11CFA
0x11ce3  ldloc.s  6
0x11ce5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class TimeZoneSyncTask.Data.Transition>::get_Current()
0x11cea  stloc.s  8
0x11cec  ldloc.3
0x11ced  ldloc.s  8
0x11cef  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0x11cf4  callvirt instance bool class [System]System.Collections.Generic.SortedSet`1<valuetype [mscorlib]System.DateTime>::Add(var<u1>)
0x11cf9  pop
0x11cfa  ldloc.s  6
0x11cfc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11d01  brtrue.s loc_11CE3
0x11d03  leave.s  loc_11D11
0x11d05  ldloc.s  6
0x11d07  brfalse.s loc_11D10
0x11d09  ldloc.s  6
0x11d0b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11d10  endfinally
0x11d11  ldloc.3
0x11d12  call     T0x2B000033
0x11d17  stloc.s  4
0x11d19  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0x11d1e  stloc.s  5
0x11d20  ldloc.s  4
0x11d22  ldloc.s  4
0x11d24  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.DateTime>::get_Count()
0x11d29  ldc.i4.1
0x11d2a  sub
0x11d2b  call     T0x2B000034
0x11d30  ldloc.s  4
0x11d32  ldc.i4.1
0x11d33  call     T0x2B000035
0x11d38  ldsfld   class [mscorlib]System.Func`3<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime, class <>f__AnonymousType4`2<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime>> <>c::<>9__1_1
0x11d3d  dup
0x11d3e  brtrue.s loc_11D57
0x11d40  pop
0x11d41  ldsfld   class <>c <>c::<>9
0x11d46  ldftn    instance class <>f__AnonymousType4`2<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime> <>c::<AmountOfTimeAccurate>b__1_1(valuetype [mscorlib]System.DateTime d1, valuetype [mscorlib]System.DateTime d2)
0x11d4c  newobj   instance void class [mscorlib]System.Func`3<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime, class <>f__AnonymousType4`2<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime>>::.ctor(object, native int)
0x11d51  dup
0x11d52  stsfld   class [mscorlib]System.Func`3<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime, class <>f__AnonymousType4`2<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime>> <>c::<>9__1_1
0x11d57  call     T0x2B000036
0x11d5c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class <>f__AnonymousType4`2<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime>>::GetEnumerator()
0x11d61  stloc.s  9
0x11d63  br.s     loc_11DA6
0x11d65  ldloc.s  9
0x11d67  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class <>f__AnonymousType4`2<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime>>::get_Current()
0x11d6c  stloc.s  0xA
0x11d6e  ldloc.s  0xA
0x11d70  callvirt instance var<u1> class <>f__AnonymousType4`2<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime>::get_IntervalStart()
0x11d75  ldloc.s  0xA
0x11d77  callvirt instance var<u1> class <>f__AnonymousType4`2<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime>::get_IntervalEnd()
0x11d7c  call     valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Utils.Helper::MidPoint(valuetype [mscorlib]System.DateTime start, valuetype [mscorlib]System.DateTime end)
0x11d81  ldarg.1
0x11d82  ldarg.2
0x11d83  call     bool TimeZoneSyncTask.Core.WindowsProjectionTransform::IsLocalTimeAccurate(valuetype [mscorlib]System.DateTime dtCurrent, valuetype TimeZoneSyncTask.Data.WindowsProjection projection, class [mscorlib]System.Collections.Generic.IEnumerable`1<class TimeZoneSyncTask.Data.Transition> transitions)
0x11d88  brfalse.s loc_11DA6
0x11d8a  ldloc.s  5
0x11d8c  ldloc.s  0xA
0x11d8e  callvirt instance var<u1> class <>f__AnonymousType4`2<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime>::get_IntervalEnd()
0x11d93  ldloc.s  0xA
0x11d95  callvirt instance var<u1> class <>f__AnonymousType4`2<valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime>::get_IntervalStart()
0x11d9a  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x11d9f  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::op_Addition(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x11da4  stloc.s  5
0x11da6  ldloc.s  9
0x11da8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11dad  brtrue.s loc_11D65
0x11daf  leave.s  loc_11DBD
0x11db1  ldloc.s  9
0x11db3  brfalse.s loc_11DBC
0x11db5  ldloc.s  9
0x11db7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11dbc  endfinally
0x11dbd  ldloc.s  5
0x11dbf  ret
```
