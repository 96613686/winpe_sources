# TimeZoneSyncTask.Core.TransitionTransform::GroupTransitionsByYear

- ea: `0x11790`
- end: `0x11b82`
- name: `TimeZoneSyncTask.Core.TransitionTransform::GroupTransitionsByYear`
- size: `1010`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task`

## callers

- `0xc6e0`

## callees

- `0xce30`
- `0xf720`
- `0xf740`
- `0xf760`
- `0xf7a0`
- `0x104d0`
- `0x104e0`
- `0x104f0`
- `0x10500`
- `0x10510`
- `0x10520`
- `0x10530`
- `0x10540`
- `0x10550`
- `0x10560`
- `0x108f0`
- `0x11790`
- `0x11b90`

## pseudocode

```c

```

## disassembly

```asm
0x11790  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::.ctor()
0x11795  stloc.0
0x11796  ldarg.1
0x11797  stloc.s  6
0x11799  br.s     loc_117EE
0x1179b  ldloc.0
0x1179c  ldloc.s  6
0x1179e  newobj   instance void TimeZoneSyncTask.Data.WindowsProjectionSet::.ctor()
0x117a3  dup
0x117a4  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan>::.ctor()
0x117a9  callvirt instance void TimeZoneSyncTask.Data.WindowsProjectionSet::set_SetUtcOffsets(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> value)
0x117ae  dup
0x117af  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::.ctor()
0x117b4  callvirt instance void TimeZoneSyncTask.Data.WindowsProjectionSet::set_ChangeUtcOffsetsDates(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> value)
0x117b9  dup
0x117ba  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::.ctor()
0x117bf  callvirt instance void TimeZoneSyncTask.Data.WindowsProjectionSet::set_SetStandardDates(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> value)
0x117c4  dup
0x117c5  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::.ctor()
0x117ca  callvirt instance void TimeZoneSyncTask.Data.WindowsProjectionSet::set_SetDaylightDates(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> value)
0x117cf  dup
0x117d0  ldc.r8   60.0
0x117d9  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x117de  callvirt instance void TimeZoneSyncTask.Data.WindowsProjectionSet::set_TsLocalStandardOffset(valuetype [mscorlib]System.TimeSpan value)
0x117e3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::set_Item(var<u1>, !!T0)
0x117e8  ldloc.s  6
0x117ea  ldc.i4.1
0x117eb  add
0x117ec  stloc.s  6
0x117ee  ldloc.s  6
0x117f0  ldarg.2
0x117f1  ble.s    loc_1179B
0x117f3  ldarg.0
0x117f4  call     T0x2B00002E
0x117f9  callvirt instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_LocalStandardOffset()
0x117fe  stloc.3
0x117ff  ldnull
0x11800  stloc.s  4
0x11802  ldarg.0
0x11803  ldsfld   class [mscorlib]System.Func`2<class TimeZoneSyncTask.Data.Transition, int32> <>c::<>9__0_0
0x11808  dup
0x11809  brtrue.s loc_11822
0x1180b  pop
0x1180c  ldsfld   class <>c <>c::<>9
0x11811  ldftn    instance int32 <>c::<GroupTransitionsByYear>b__0_0(class TimeZoneSyncTask.Data.Transition t)
0x11817  newobj   instance void class [mscorlib]System.Func`2<class TimeZoneSyncTask.Data.Transition, int32>::.ctor(object, native int)
0x1181c  dup
0x1181d  stsfld   class [mscorlib]System.Func`2<class TimeZoneSyncTask.Data.Transition, int32> <>c::<>9__0_0
0x11822  call     T0x2B00002F
0x11827  stloc.s  5
0x11829  ldarg.0
0x1182a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class TimeZoneSyncTask.Data.Transition>::GetEnumerator()
0x1182f  stloc.s  7
0x11831  br       loc_11AA2
0x11836  ldloc.s  7
0x11838  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class TimeZoneSyncTask.Data.Transition>::get_Current()
0x1183d  stloc.s  8
0x1183f  ldloc.s  8
0x11841  callvirt instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_UtcOffset()
0x11846  stloc.1
0x11847  ldloc.s  8
0x11849  callvirt instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_LocalStandardOffset()
0x1184e  stloc.2
0x1184f  ldloc.2
0x11850  ldloc.3
0x11851  call     bool [mscorlib]System.TimeSpan::op_Inequality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x11856  brfalse  loc_119CD
0x1185b  ldloc.3
0x1185c  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0x11861  call     bool [mscorlib]System.TimeSpan::op_Equality(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x11866  brfalse.s loc_118C3
0x11868  ldloc.s  4
0x1186a  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_LocalTransitionTime()
0x1186f  stloc.s  9
0x11871  ldloca.s 9
0x11873  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x11878  ldarg.1
0x11879  blt      loc_11916
0x1187e  ldloc.s  4
0x11880  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_LocalTransitionTime()
0x11885  stloc.s  9
0x11887  ldloca.s 9
0x11889  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x1188e  ldarg.2
0x1188f  bgt      loc_11916
0x11894  ldloc.0
0x11895  ldloc.s  4
0x11897  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_LocalTransitionTime()
0x1189c  stloc.s  9
0x1189e  ldloca.s 9
0x118a0  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x118a5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::get_Item(void)
0x118aa  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetDaylightDates()
0x118af  ldloc.s  4
0x118b1  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0x118b6  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x118bb  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::Add(var<u1>)
0x118c0  pop
0x118c1  br.s     loc_11916
0x118c3  ldloc.s  4
0x118c5  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_LocalTransitionTime()
0x118ca  stloc.s  9
0x118cc  ldloca.s 9
0x118ce  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x118d3  ldarg.1
0x118d4  blt.s    loc_11916
0x118d6  ldloc.s  4
0x118d8  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_LocalTransitionTime()
0x118dd  stloc.s  9
0x118df  ldloca.s 9
0x118e1  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x118e6  ldarg.2
0x118e7  bgt.s    loc_11916
0x118e9  ldloc.0
0x118ea  ldloc.s  4
0x118ec  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_LocalTransitionTime()
0x118f1  stloc.s  9
0x118f3  ldloca.s 9
0x118f5  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x118fa  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::get_Item(void)
0x118ff  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetStandardDates()
0x11904  ldloc.s  4
0x11906  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0x1190b  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x11910  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::Add(var<u1>)
0x11915  pop
0x11916  ldloc.s  4
0x11918  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_LocalTransitionTime()
0x1191d  stloc.s  9
0x1191f  ldloca.s 9
0x11921  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x11926  ldarg.1
0x11927  blt      loc_119CD
0x1192c  ldloc.s  4
0x1192e  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_LocalTransitionTime()
0x11933  stloc.s  9
0x11935  ldloca.s 9
0x11937  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x1193c  ldarg.2
0x1193d  bgt      loc_119CD
0x11942  ldloc.0
0x11943  ldloc.s  4
0x11945  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_LocalTransitionTime()
0x1194a  stloc.s  9
0x1194c  ldloca.s 9
0x1194e  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x11953  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::get_Item(void)
0x11958  callvirt instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.WindowsProjectionSet::get_TsLocalStandardOffset()
0x1195d  stloc.s  0xA
0x1195f  ldloc.0
0x11960  ldloc.s  4
0x11962  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_LocalTransitionTime()
0x11967  stloc.s  9
0x11969  ldloca.s 9
0x1196b  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x11970  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::get_Item(void)
0x11975  ldloc.s  0xA
0x11977  ldloc.s  4
0x11979  callvirt instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_LocalStandardOffset()
0x1197e  call     bool [mscorlib]System.TimeSpan::op_LessThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x11983  brtrue.s loc_119C1
0x11985  ldloc.s  4
0x11987  callvirt instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_LocalStandardOffset()
0x1198c  ldc.r8   1.0
0x11995  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x1199a  call     bool [mscorlib]System.TimeSpan::op_GreaterThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1199f  brfalse.s loc_119BD
0x119a1  ldloc.s  4
0x119a3  callvirt instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_LocalStandardOffset()
0x119a8  ldc.r8   59.0
0x119b1  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x119b6  call     bool [mscorlib]System.TimeSpan::op_LessThanOrEqual(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x119bb  brtrue.s loc_119C1
0x119bd  ldloc.s  0xA
0x119bf  br.s     loc_119C8
0x119c1  ldloc.s  4
0x119c3  callvirt instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Transition::get_LocalStandardOffset()
0x119c8  callvirt instance void TimeZoneSyncTask.Data.WindowsProjectionSet::set_TsLocalStandardOffset(valuetype [mscorlib]System.TimeSpan value)
0x119cd  ldloc.s  5
0x119cf  ldarg.1
0x119d0  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x119d5  ldc.i4.0
0x119d6  ldloc.s  8
0x119d8  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_LocalTransitionTime()
0x119dd  stloc.s  9
0x119df  ldloca.s 9
0x119e1  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x119e6  ldarg.2
0x119e7  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x119ec  ldloc.s  5
0x119ee  ldarg.1
0x119ef  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x119f4  sub
0x119f5  ldc.i4.1
0x119f6  add
0x119f7  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x119fc  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<int32> [System.Core]System.Linq.Enumerable::Range(int32, int32)
0x11a01  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<int32>::GetEnumerator()
0x11a06  stloc.s  0xB
0x11a08  br.s     loc_11A73
0x11a0a  ldloc.s  0xB
0x11a0c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<int32>::get_Current()
0x11a11  stloc.s  0xC
0x11a13  ldloc.s  0xC
0x11a15  ldarg.1
0x11a16  blt.s    loc_11A73
0x11a18  ldloc.s  0xC
0x11a1a  ldarg.2
0x11a1b  bgt.s    loc_11A73
0x11a1d  ldloc.0
0x11a1e  ldloc.s  0xC
0x11a20  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::get_Item(void)
0x11a25  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets()
0x11a2a  ldloc.1
0x11a2b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan>::Add(var<u1>)
0x11a30  pop
0x11a31  ldloc.s  8
0x11a33  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_LocalTransitionTime()
0x11a38  call     bool TimeZoneSyncTask.Core.TransitionTransform::IsBeginningOfYear(valuetype [mscorlib]System.DateTime dt)
0x11a3d  brtrue.s loc_11A73
0x11a3f  ldloc.0
0x11a40  ldloc.s  0xC
0x11a42  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::get_Item(void)
0x11a47  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets()
0x11a4c  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan>::get_Count()
0x11a51  ldc.i4.1
0x11a52  ble.s    loc_11A73
0x11a54  ldloc.0
0x11a55  ldloc.s  0xC
0x11a57  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::get_Item(void)
0x11a5c  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_ChangeUtcOffsetsDates()
0x11a61  ldloc.s  4
0x11a63  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0x11a68  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x11a6d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::Add(var<u1>)
0x11a72  pop
0x11a73  ldloc.s  0xB
0x11a75  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11a7a  brtrue.s loc_11A0A
0x11a7c  leave.s  loc_11A8A
0x11a7e  ldloc.s  0xB
0x11a80  brfalse.s loc_11A89
0x11a82  ldloc.s  0xB
0x11a84  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11a89  endfinally
0x11a8a  ldloc.s  8
0x11a8c  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_LocalTransitionTime()
0x11a91  stloc.s  9
0x11a93  ldloca.s 9
0x11a95  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x11a9a  stloc.s  5
0x11a9c  ldloc.2
0x11a9d  stloc.3
0x11a9e  ldloc.s  8
0x11aa0  stloc.s  4
0x11aa2  ldloc.s  7
0x11aa4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11aa9  brtrue   loc_11836
0x11aae  leave.s  loc_11ABC
0x11ab0  ldloc.s  7
0x11ab2  brfalse.s loc_11ABB
0x11ab4  ldloc.s  7
0x11ab6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11abb  endfinally
0x11abc  ldloc.0
0x11abd  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::GetEnumerator()
0x11ac2  stloc.s  0xD
0x11ac4  br       loc_11B64
0x11ac9  ldloca.s 0xD
0x11acb  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::get_Current()
0x11ad0  stloc.s  0xE
0x11ad2  ldloca.s 0xE
0x11ad4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::get_Value()
0x11ad9  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetDaylightDates()
0x11ade  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::get_Count()
0x11ae3  brtrue.s loc_11B01
0x11ae5  ldloca.s 0xE
0x11ae7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::get_Value()
0x11aec  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetDaylightDates()
0x11af1  ldloca.s 0xF
0x11af3  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x11af9  ldloc.s  0xF
0x11afb  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::Add(var<u1>)
0x11b00  pop
0x11b01  ldloca.s 0xE
0x11b03  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::get_Value()
0x11b08  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetStandardDates()
0x11b0d  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::get_Count()
0x11b12  brtrue.s loc_11B30
0x11b14  ldloca.s 0xE
0x11b16  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::get_Value()
0x11b1b  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetStandardDates()
0x11b20  ldloca.s 0xF
0x11b22  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x11b28  ldloc.s  0xF
0x11b2a  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>>::Add(var<u1>)
0x11b2f  pop
0x11b30  ldloca.s 0xE
0x11b32  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>::get_Value()
0x11b37  callvirt instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.TimeSpan> TimeZoneSyncTask.Data.WindowsProjectionSet::get_SetUtcOffsets()
  ... truncated ...
```
