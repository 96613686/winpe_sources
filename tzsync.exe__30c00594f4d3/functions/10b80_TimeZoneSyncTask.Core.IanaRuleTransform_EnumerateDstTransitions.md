# TimeZoneSyncTask.Core.IanaRuleTransform::EnumerateDstTransitions

- ea: `0x10b80`
- end: `0x10db8`
- name: `TimeZoneSyncTask.Core.IanaRuleTransform::EnumerateDstTransitions`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `service_task`

## callers

- `0x10970`

## callees

- `0xe980`
- `0xea40`
- `0xebf0`
- `0xec60`
- `0xf030`
- `0xf050`
- `0xf070`
- `0xf090`
- `0xf0b0`
- `0xf0d0`
- `0xf730`
- `0xf750`
- `0xf770`
- `0xf790`
- `0xf8e0`
- `0x10b80`
- `0x10dc0`
- `0x10ec0`
- `0x10ed0`
- `0x10ee0`
- `0x10ef0`
- `0x10f00`
- `0x10f10`
- `0x10f40`
- `0x10f60`
- `0x10f80`
- `0x10fe0`

## pseudocode

```c

```

## disassembly

```asm
0x10b80  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition>::.ctor()
0x10b85  stloc.0
0x10b86  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Core.TransitionEvent>::.ctor()
0x10b8b  stloc.1
0x10b8c  ldarg.0
0x10b8d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>::GetEnumerator()
0x10b92  stloc.2
0x10b93  br       loc_10C2D
0x10b98  ldloc.2
0x10b99  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>::get_Current()
0x10b9e  stloc.3
0x10b9f  ldloca.s 3
0x10ba1  call     instance int32 TimeZoneSyncTask.Data.DstTransitionRule::get_From()
0x10ba6  ldarga.s 1
0x10ba8  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x10bad  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x10bb2  stloc.s  4
0x10bb4  br.s     loc_10C0B
0x10bb6  ldloc.1
0x10bb7  ldloca.s 5
0x10bb9  initobj  TimeZoneSyncTask.Core.TransitionEvent
0x10bbf  ldloca.s 5
0x10bc1  ldloca.s 3
0x10bc3  call     instance valuetype TimeZoneSyncTask.Data.TimeOfDay TimeZoneSyncTask.Data.DstTransitionRule::get_At()
0x10bc8  call     instance void TimeZoneSyncTask.Core.TransitionEvent::set_At(valuetype TimeZoneSyncTask.Data.TimeOfDay value)
0x10bcd  ldloca.s 5
0x10bcf  ldloca.s 3
0x10bd1  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.DstTransitionRule::get_Save()
0x10bd6  call     instance void TimeZoneSyncTask.Core.TransitionEvent::set_Save(valuetype [mscorlib]System.TimeSpan value)
0x10bdb  ldloca.s 5
0x10bdd  ldloc.s  4
0x10bdf  ldloca.s 3
0x10be1  call     instance int32 TimeZoneSyncTask.Data.DstTransitionRule::get_In()
0x10be6  ldloca.s 3
0x10be8  call     instance valuetype TimeZoneSyncTask.Data.DayOfMonth TimeZoneSyncTask.Data.DstTransitionRule::get_On()
0x10bed  ldloca.s 3
0x10bef  call     instance valuetype TimeZoneSyncTask.Data.TimeOfDay TimeZoneSyncTask.Data.DstTransitionRule::get_At()
0x10bf4  call     valuetype TimeZoneSyncTask.Data.DateTimeEx TimeZoneSyncTask.Utils.Helper::FromTzdbDate(int32 year, int32 month, valuetype TimeZoneSyncTask.Data.DayOfMonth on, valuetype TimeZoneSyncTask.Data.TimeOfDay at)
0x10bf9  call     instance void TimeZoneSyncTask.Core.TransitionEvent::set_TransitionTime(valuetype TimeZoneSyncTask.Data.DateTimeEx value)
0x10bfe  ldloc.s  5
0x10c00  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Core.TransitionEvent>::Add(var<u1>)
0x10c05  ldloc.s  4
0x10c07  ldc.i4.1
0x10c08  add
0x10c09  stloc.s  4
0x10c0b  ldloc.s  4
0x10c0d  ldarga.s 2
0x10c0f  call     instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.DateTimeEx::get_Time()
0x10c14  stloc.s  6
0x10c16  ldloca.s 6
0x10c18  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x10c1d  ldc.i4.1
0x10c1e  add
0x10c1f  ldloca.s 3
0x10c21  call     instance int32 TimeZoneSyncTask.Data.DstTransitionRule::get_To()
0x10c26  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x10c2b  ble.s    loc_10BB6
0x10c2d  ldloc.2
0x10c2e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10c33  brtrue   loc_10B98
0x10c38  leave.s  loc_10C44
0x10c3a  ldloc.2
0x10c3b  brfalse.s loc_10C43
0x10c3d  ldloc.2
0x10c3e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10c43  endfinally
0x10c44  ldloc.1
0x10c45  ldsfld   class [mscorlib]System.Comparison`1<valuetype TimeZoneSyncTask.Core.TransitionEvent> <>c::<>9__1_0
0x10c4a  dup
0x10c4b  brtrue.s loc_10C64
0x10c4d  pop
0x10c4e  ldsfld   class <>c <>c::<>9
0x10c53  ldftn    instance int32 <>c::<EnumerateDstTransitions>b__1_0(valuetype TimeZoneSyncTask.Core.TransitionEvent x, valuetype TimeZoneSyncTask.Core.TransitionEvent y)
0x10c59  newobj   instance void class [mscorlib]System.Comparison`1<valuetype TimeZoneSyncTask.Core.TransitionEvent>::.ctor(object, native int)
0x10c5e  dup
0x10c5f  stsfld   class [mscorlib]System.Comparison`1<valuetype TimeZoneSyncTask.Core.TransitionEvent> <>c::<>9__1_0
0x10c64  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Core.TransitionEvent>::Sort(class [mscorlib]System.Comparison`1<var<u1>>)
0x10c69  ldloc.1
0x10c6a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Core.TransitionEvent>::GetEnumerator()
0x10c6f  stloc.s  7
0x10c71  br       loc_10D75
0x10c76  ldloca.s 7
0x10c78  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype TimeZoneSyncTask.Core.TransitionEvent>::get_Current()
0x10c7d  stloc.s  8
0x10c7f  ldloca.s 8
0x10c81  call     instance valuetype TimeZoneSyncTask.Data.DateTimeEx TimeZoneSyncTask.Core.TransitionEvent::get_TransitionTime()
0x10c86  ldarg.3
0x10c87  ldarg.s  4
0x10c89  ldobj    [mscorlib]System.TimeSpan
0x10c8e  call     valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Utils.Helper::ConvertToUtc(valuetype TimeZoneSyncTask.Data.DateTimeEx dtx, valuetype [mscorlib]System.TimeSpan tsUtcOffset, valuetype [mscorlib]System.TimeSpan tsLocalStandardOffset)
0x10c93  stloc.s  9
0x10c95  ldloc.s  9
0x10c97  ldarg.1
0x10c98  call     bool [mscorlib]System.DateTime::op_GreaterThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x10c9d  brfalse  loc_10D75
0x10ca2  ldloca.s 0xA
0x10ca4  initobj  TimeZoneSyncTask.Core.DateTimeWithOffset
0x10caa  ldloca.s 0xA
0x10cac  ldloc.s  9
0x10cae  call     instance void TimeZoneSyncTask.Core.DateTimeWithOffset::set_Time(valuetype [mscorlib]System.DateTime value)
0x10cb3  ldloca.s 0xA
0x10cb5  ldarg.3
0x10cb6  call     instance void TimeZoneSyncTask.Core.DateTimeWithOffset::set_TsUtcOffset(valuetype [mscorlib]System.TimeSpan value)
0x10cbb  ldloca.s 0xA
0x10cbd  ldarg.s  4
0x10cbf  ldobj    [mscorlib]System.TimeSpan
0x10cc4  call     instance void TimeZoneSyncTask.Core.DateTimeWithOffset::set_TsLocalStandardOffset(valuetype [mscorlib]System.TimeSpan value)
0x10cc9  ldloca.s 0xA
0x10ccb  ldarg.2
0x10ccc  call     instance int32 TimeZoneSyncTask.Core.DateTimeWithOffset::Compare(valuetype TimeZoneSyncTask.Data.DateTimeEx dtx)
0x10cd1  ldc.i4.0
0x10cd2  bge      loc_10D75
0x10cd7  ldarg.s  4
0x10cd9  ldobj    [mscorlib]System.TimeSpan
0x10cde  ldloca.s 8
0x10ce0  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Core.TransitionEvent::get_Save()
0x10ce5  call     bool [mscorlib]System.TimeSpan::op_Inequality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x10cea  brfalse  loc_10D75
0x10cef  ldloc.0
0x10cf0  newobj   instance void TimeZoneSyncTask.Data.Transition::.ctor()
0x10cf5  dup
0x10cf6  ldarg.3
0x10cf7  callvirt instance void TimeZoneSyncTask.Data.Transition::set_UtcOffset(valuetype [mscorlib]System.TimeSpan value)
0x10cfc  dup
0x10cfd  ldarg.s  4
0x10cff  ldobj    [mscorlib]System.TimeSpan
0x10d04  callvirt instance void TimeZoneSyncTask.Data.Transition::set_LocalStandardOffset(valuetype [mscorlib]System.TimeSpan value)
0x10d09  dup
0x10d0a  ldloc.s  9
0x10d0c  callvirt instance void TimeZoneSyncTask.Data.Transition::set_TransitionTime(valuetype [mscorlib]System.DateTime value)
0x10d11  dup
0x10d12  ldloc.s  9
0x10d14  ldarg.s  4
0x10d16  ldobj    [mscorlib]System.TimeSpan
0x10d1b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x10d20  ldarg.3
0x10d21  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x10d26  call     bool TimeZoneSyncTask.Utils.Helper::IsMidnight(valuetype [mscorlib]System.DateTime dt)
0x10d2b  brtrue.s loc_10D30
0x10d2d  ldc.i4.0
0x10d2e  br.s     loc_10D5D
0x10d30  ldloca.s 8
0x10d32  call     instance valuetype TimeZoneSyncTask.Data.TimeOfDay TimeZoneSyncTask.Core.TransitionEvent::get_At()
0x10d37  ldarg.3
0x10d38  ldarg.s  4
0x10d3a  ldobj    [mscorlib]System.TimeSpan
0x10d3f  call     valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Core.IanaRuleTransform::GetLocalTimeOfDay(valuetype TimeZoneSyncTask.Data.TimeOfDay tod, valuetype [mscorlib]System.TimeSpan tsUtcOffset, valuetype [mscorlib]System.TimeSpan tsLocalStandardOffset)
0x10d44  ldc.r8   24.0
0x10d4d  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromHours(float64)
0x10d52  call     bool [mscorlib]System.TimeSpan::op_Equality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x10d57  brtrue.s loc_10D5C
0x10d59  ldc.i4.1
0x10d5a  br.s     loc_10D5D
0x10d5c  ldc.i4.2
0x10d5d  callvirt instance void TimeZoneSyncTask.Data.Transition::set_Type(valuetype TimeZoneSyncTask.Data.MidnightTransitionType value)
0x10d62  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition>::Add(var<u1>)
0x10d67  ldarg.s  4
0x10d69  ldloca.s 8
0x10d6b  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Core.TransitionEvent::get_Save()
0x10d70  stobj    [mscorlib]System.TimeSpan
0x10d75  ldloca.s 7
0x10d77  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype TimeZoneSyncTask.Core.TransitionEvent>::MoveNext()
0x10d7c  brtrue   loc_10C76
0x10d81  leave.s  loc_10D91
0x10d83  ldloca.s 7
0x10d85  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype TimeZoneSyncTask.Core.TransitionEvent>
0x10d8b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10d90  endfinally
0x10d91  ldloc.0
0x10d92  ldsfld   class [mscorlib]System.Comparison`1<class TimeZoneSyncTask.Data.Transition> <>c::<>9__1_1
0x10d97  dup
0x10d98  brtrue.s loc_10DB1
0x10d9a  pop
0x10d9b  ldsfld   class <>c <>c::<>9
0x10da0  ldftn    instance int32 <>c::<EnumerateDstTransitions>b__1_1(class TimeZoneSyncTask.Data.Transition x, class TimeZoneSyncTask.Data.Transition y)
0x10da6  newobj   instance void class [mscorlib]System.Comparison`1<class TimeZoneSyncTask.Data.Transition>::.ctor(object, native int)
0x10dab  dup
0x10dac  stsfld   class [mscorlib]System.Comparison`1<class TimeZoneSyncTask.Data.Transition> <>c::<>9__1_1
0x10db1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition>::Sort(class [mscorlib]System.Comparison`1<var<u1>>)
0x10db6  ldloc.0
0x10db7  ret
```
