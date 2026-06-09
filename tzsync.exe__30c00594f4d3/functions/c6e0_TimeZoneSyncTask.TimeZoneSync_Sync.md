# TimeZoneSyncTask.TimeZoneSync::Sync

- ea: `0xc6e0`
- end: `0xcdde`
- name: `TimeZoneSyncTask.TimeZoneSync::Sync`
- size: `1790`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, service_task`

## callers

- `0xc470`

## callees

- `0x1050`
- `0xc6e0`
- `0xcde0`
- `0xce40`
- `0xcfb0`
- `0xcff0`
- `0xd2c0`
- `0xd960`
- `0xd990`
- `0xd9c0`
- `0xd9f0`
- `0xda10`
- `0xda60`
- `0x10320`
- `0x10340`
- `0x108c0`
- `0x10970`
- `0x11030`
- `0x11550`
- `0x11790`
- `0x120f0`
- `0x121c0`
- `0x127b0`
- `0x127d0`
- `0x140d0`

## string_xrefs

- `0xc71e`: `Registry`
- `0xcb8c`: `Registry`
- `0xccc2`: `Deleted registry from year: {0} to year :{1} for tzid : {2}`
- `0xccf9`: `Deleted registry from year: {0} to year :{1} for tzid : {2}`

## pseudocode

```c

```

## disassembly

```asm
0xc6e0  ldarg.0
0xc6e1  ldfld    class [mscorlib]System.IO.Stream TimeZoneSyncTask.TimeZoneSync::stmTimeZone
0xc6e6  brfalse.s loc_C6FD
0xc6e8  ldarg.0
0xc6e9  ldfld    class [mscorlib]System.IO.Stream TimeZoneSyncTask.TimeZoneSync::stmMapping
0xc6ee  brfalse.s loc_C6FD
0xc6f0  ldarg.0
0xc6f1  ldfld    string TimeZoneSyncTask.TimeZoneSync::pathTimeZoneRoot
0xc6f6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc6fb  brfalse.s loc_C708
0xc6fd  ldstr    aInvalidInput// "Invalid input"
0xc702  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xc707  throw
0xc708  nop
0xc709  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0xc70e  ldarg.0
0xc70f  ldfld    string TimeZoneSyncTask.TimeZoneSync::pathTimeZoneRoot
0xc714  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0xc719  stloc.0
0xc71a  ldloc.0
0xc71b  ldnull
0xc71c  cgt.un
0xc71e  ldstr    aRegistry// "Registry"
0xc723  ldstr    aExpectingNonNu// "expecting non-null time zone root regke"...
0xc728  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string exceptiontype, string msg)
0xc72d  ldarg.0
0xc72e  ldfld    class [mscorlib]System.IO.Stream TimeZoneSyncTask.TimeZoneSync::stmMapping
0xc733  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> TimeZoneSyncTask.Core.XmlDataTransform::ParseTimeZoneMapping(class [mscorlib]System.IO.Stream stmMapping)
0xc738  stloc.1
0xc739  ldloc.1
0xc73a  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__9_0
0xc73f  dup
0xc740  brtrue.s loc_C759
0xc742  pop
0xc743  ldsfld   class <>c <>c::<>9
0xc748  ldftn    instance string <>c::<Sync>b__9_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> kv)
0xc74e  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string>::.ctor(object, native int)
0xc753  dup
0xc754  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__9_0
0xc759  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__9_1
0xc75e  dup
0xc75f  brtrue.s loc_C778
0xc761  pop
0xc762  ldsfld   class <>c <>c::<>9
0xc767  ldftn    instance string <>c::<Sync>b__9_1(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> kv)
0xc76d  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string>::.ctor(object, native int)
0xc772  dup
0xc773  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__9_1
0xc778  call     T0x2B000003
0xc77d  stloc.2
0xc77e  ldloc.0
0xc77f  ldloc.1
0xc780  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<int32, int32>> TimeZoneSyncTask.DynamicDstTransform::GetDynamicDstRange(class [mscorlib]Microsoft.Win32.RegistryKey rkTimeZoneRoot, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> mapWinTzToTzid)
0xc785  stloc.3
0xc786  ldarg.0
0xc787  ldfld    class [mscorlib]System.IO.Stream TimeZoneSyncTask.TimeZoneSync::stmTimeZone
0xc78c  ldloc.3
0xc78d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<int32, int32>>::get_Keys()
0xc792  call     class TimeZoneSyncTask.Core.TimeZoneData TimeZoneSyncTask.Core.XmlDataTransform::ParseTimeZoneData(class [mscorlib]System.IO.Stream stmTimeZone, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> rgZones)
0xc797  stloc.s  4
0xc799  ldsfld   class TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER TimeZoneSyncTask.Program::eventProvider
0xc79e  callvirt instance bool TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteInitializationStop()
0xc7a3  pop
0xc7a4  ldstr    a0TzidReference// "{0} tzid referenced"
0xc7a9  ldloc.s  4
0xc7ab  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>> TimeZoneSyncTask.Core.TimeZoneData::get_MapZoneToRules()
0xc7b0  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>>::get_Count()
0xc7b5  box      [mscorlib]System.Int32
0xc7ba  call     string [mscorlib]System.String::Format(string, object)
0xc7bf  stloc.s  5
0xc7c1  ldloc.s  5
0xc7c3  ldstr    a0TimezoneruleU// "{0} TimeZoneRule used"
0xc7c8  ldloc.s  4
0xc7ca  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>> TimeZoneSyncTask.Core.TimeZoneData::get_MapZoneToRules()
0xc7cf  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>>::get_Values()
0xc7d4  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>, int32> <>c::<>9__9_2
0xc7d9  dup
0xc7da  brtrue.s loc_C7F3
0xc7dc  pop
0xc7dd  ldsfld   class <>c <>c::<>9
0xc7e2  ldftn    instance int32 <>c::<Sync>b__9_2(class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule> l)
0xc7e8  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>, int32>::.ctor(object, native int)
0xc7ed  dup
0xc7ee  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>, int32> <>c::<>9__9_2
0xc7f3  call     T0x2B000004
0xc7f8  call     int32 [System.Core]System.Linq.Enumerable::Sum(class [mscorlib]System.Collections.Generic.IEnumerable`1<int32>)
0xc7fd  box      [mscorlib]System.Int32
0xc802  call     string [mscorlib]System.String::Format(string, object)
0xc807  call     string [mscorlib]System.String::Concat(string, string)
0xc80c  stloc.s  5
0xc80e  ldloc.s  5
0xc810  ldstr    a0RulesReferenc// "{0} rules referenced"
0xc815  ldloc.s  4
0xc817  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>> TimeZoneSyncTask.Core.TimeZoneData::get_MapDstToRules()
0xc81c  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>>::get_Count()
0xc821  box      [mscorlib]System.Int32
0xc826  call     string [mscorlib]System.String::Format(string, object)
0xc82b  call     string [mscorlib]System.String::Concat(string, string)
0xc830  stloc.s  5
0xc832  ldloc.s  5
0xc834  ldstr    a0Dsttransition// "{0} DstTransitionRule used"
0xc839  ldloc.s  4
0xc83b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>> TimeZoneSyncTask.Core.TimeZoneData::get_MapDstToRules()
0xc840  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>>::get_Values()
0xc845  ldsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>, int32> <>c::<>9__9_3
0xc84a  dup
0xc84b  brtrue.s loc_C864
0xc84d  pop
0xc84e  ldsfld   class <>c <>c::<>9
0xc853  ldftn    instance int32 <>c::<Sync>b__9_3(class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule> l)
0xc859  newobj   instance void class [mscorlib]System.Func`2<class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>, int32>::.ctor(object, native int)
0xc85e  dup
0xc85f  stsfld   class [mscorlib]System.Func`2<class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>, int32> <>c::<>9__9_3
0xc864  call     T0x2B000005
0xc869  call     int32 [System.Core]System.Linq.Enumerable::Sum(class [mscorlib]System.Collections.Generic.IEnumerable`1<int32>)
0xc86e  box      [mscorlib]System.Int32
0xc873  call     string [mscorlib]System.String::Format(string, object)
0xc878  call     string [mscorlib]System.String::Concat(string, string)
0xc87d  stloc.s  5
0xc87f  ldloc.3
0xc880  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<int32, int32>>::GetEnumerator()
0xc885  stloc.s  6
0xc887  br       loc_C922
0xc88c  ldloca.s 6
0xc88e  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Tuple`2<int32, int32>>::get_Current()
0xc893  stloc.s  7
0xc895  call     bool Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::get_IsEnabled()
0xc89a  brfalse.s loc_C8E0
0xc89c  ldstr    aMapsTzid0ToRan// "maps tzid {0} to range ({1}, {2})"
0xc8a1  ldc.i4.3
0xc8a2  newarr   [mscorlib]System.Object
0xc8a7  dup
0xc8a8  ldc.i4.0
0xc8a9  ldloca.s 7
0xc8ab  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Tuple`2<int32, int32>>::get_Key()
0xc8b0  stelem.ref
0xc8b1  dup
0xc8b2  ldc.i4.1
0xc8b3  ldloca.s 7
0xc8b5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Tuple`2<int32, int32>>::get_Value()
0xc8ba  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, int32>::get_Item1()
0xc8bf  box      [mscorlib]System.Int32
0xc8c4  stelem.ref
0xc8c5  dup
0xc8c6  ldc.i4.2
0xc8c7  ldloca.s 7
0xc8c9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Tuple`2<int32, int32>>::get_Value()
0xc8ce  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, int32>::get_Item2()
0xc8d3  box      [mscorlib]System.Int32
0xc8d8  stelem.ref
0xc8d9  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceInfo(string format, object[] args)
0xc8de  br.s     loc_C922
0xc8e0  ldstr    aMapsTzid0ToRan// "maps tzid {0} to range ({1}, {2})"
0xc8e5  ldc.i4.3
0xc8e6  newarr   [mscorlib]System.Object
0xc8eb  dup
0xc8ec  ldc.i4.0
0xc8ed  ldloca.s 7
0xc8ef  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Tuple`2<int32, int32>>::get_Key()
0xc8f4  stelem.ref
0xc8f5  dup
0xc8f6  ldc.i4.1
0xc8f7  ldloca.s 7
0xc8f9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Tuple`2<int32, int32>>::get_Value()
0xc8fe  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, int32>::get_Item1()
0xc903  box      [mscorlib]System.Int32
0xc908  stelem.ref
0xc909  dup
0xc90a  ldc.i4.2
0xc90b  ldloca.s 7
0xc90d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Tuple`2<int32, int32>>::get_Value()
0xc912  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, int32>::get_Item2()
0xc917  box      [mscorlib]System.Int32
0xc91c  stelem.ref
0xc91d  call     void [System]System.Diagnostics.Trace::TraceInformation(string, object[])
0xc922  ldloca.s 6
0xc924  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Tuple`2<int32, int32>>::MoveNext()
0xc929  brtrue   loc_C88C
0xc92e  leave.s  loc_C93E
0xc930  ldloca.s 6
0xc932  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Tuple`2<int32, int32>>
0xc938  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc93d  endfinally
0xc93e  ldsfld   class TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER TimeZoneSyncTask.Program::eventProvider
0xc943  callvirt instance bool TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteConversionStart()
0xc948  pop
0xc949  ldloc.3
0xc94a  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Tuple`2<int32, int32>>::GetEnumerator()
0xc94f  stloc.s  6
0xc951  br       loc_CD8F
0xc956  ldloca.s 6
0xc958  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Tuple`2<int32, int32>>::get_Current()
0xc95d  stloc.s  8
0xc95f  newobj   instance void <>c__DisplayClass9_0::.ctor()
0xc964  stloc.s  9
0xc966  ldloc.s  9
0xc968  ldarg.0
0xc969  stfld    class TimeZoneSyncTask.TimeZoneSync <>c__DisplayClass9_0::<>4__this
0xc96e  ldsfld   class TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER TimeZoneSyncTask.Program::eventProvider
0xc973  ldloca.s 8
0xc975  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Tuple`2<int32, int32>>::get_Key()
0xc97a  callvirt instance bool TimeZoneSyncTask.WINDOWS_TZSYNC_ETW_PROVIDER::EventWriteTzItemConversionStart(string TimeZoneId)
0xc97f  pop
0xc980  ldloca.s 8
0xc982  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Tuple`2<int32, int32>>::get_Value()
0xc987  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, int32>::get_Item1()
0xc98c  stloc.s  0xA
0xc98e  ldloca.s 8
0xc990  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Tuple`2<int32, int32>>::get_Value()
0xc995  callvirt instance var<u1> class [mscorlib]System.Tuple`2<int32, int32>::get_Item2()
0xc99a  stloc.s  0xB
0xc99c  ldloc.s  0xA
0xc99e  ldc.i4   0x7E0
0xc9a3  blt.s    loc_C9A9
0xc9a5  ldloc.s  0xA
0xc9a7  br.s     loc_C9AE
0xc9a9  ldc.i4   0x7E0
0xc9ae  stloc.s  0xC
0xc9b0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0xc9b5  stloc.s  0x10
0xc9b7  ldloca.s 0x10
0xc9b9  call     instance int32 [mscorlib]System.DateTime::get_Year()
0xc9be  ldc.i4.1
0xc9bf  add
0xc9c0  stloc.s  0xD
0xc9c2  ldloc.s  9
0xc9c4  ldloc.s  4
0xc9c6  ldloca.s 8
0xc9c8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Tuple`2<int32, int32>>::get_Key()
0xc9cd  ldloc.s  0xC
0xc9cf  ldloc.s  0xD
0xc9d1  call     class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition> TimeZoneSyncTask.Core.IanaRuleTransform::ComputeTransitions(class TimeZoneSyncTask.Core.TimeZoneData data, string tzid, int32 minYear, int32 maxYear)
0xc9d6  stfld    class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition> <>c__DisplayClass9_0::rgTransitions
0xc9db  ldloc.s  5
0xc9dd  ldstr    a0TransitionsFo// "{0} transitions for {1}"
0xc9e2  ldloc.s  9
0xc9e4  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition> <>c__DisplayClass9_0::rgTransitions
0xc9e9  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition>::get_Count()
0xc9ee  box      [mscorlib]System.Int32
0xc9f3  ldloca.s 8
0xc9f5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Tuple`2<int32, int32>>::get_Key()
0xc9fa  call     string [mscorlib]System.String::Format(string, object, object)
0xc9ff  call     string [mscorlib]System.String::Concat(string, string)
0xca04  stloc.s  5
0xca06  ldloc.s  9
0xca08  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition> <>c__DisplayClass9_0::rgTransitions
0xca0d  ldloc.s  0xC
0xca0f  ldloc.s  0xD
0xca11  call     class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet> TimeZoneSyncTask.Core.TransitionTransform::GroupTransitionsByYear(class [mscorlib]System.Collections.Generic.IEnumerable`1<class TimeZoneSyncTask.Data.Transition> transitions, int32 minYear, int32 maxYear)
0xca16  stloc.s  0xE
0xca18  ldloc.s  0xE
0xca1a  ldarg.0
0xca1b  ldftn    instance bool TimeZoneSyncTask.TimeZoneSync::<Sync>b__9_4(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet> kv)
0xca21  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>, bool>::.ctor(object, native int)
0xca26  call     T0x2B000006
0xca2b  ldloc.s  9
0xca2d  ldftn    instance class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>, valuetype [mscorlib]System.Nullable`1<valuetype TimeZoneSyncTask.Data.WindowsProjection>> <>c__DisplayClass9_0::<Sync>b__5(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet> kv)
0xca33  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>, class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>, valuetype [mscorlib]System.Nullable`1<valuetype TimeZoneSyncTask.Data.WindowsProjection>>>::.ctor(object, native int)
0xca38  call     T0x2B000007
0xca3d  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>, valuetype [mscorlib]System.Nullable`1<valuetype TimeZoneSyncTask.Data.WindowsProjection>>, bool> <>c::<>9__9_6
0xca42  dup
0xca43  brtrue.s loc_CA5C
0xca45  pop
0xca46  ldsfld   class <>c <>c::<>9
0xca4b  ldftn    instance bool <>c::<Sync>b__9_6(class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>, valuetype [mscorlib]System.Nullable`1<valuetype TimeZoneSyncTask.Data.WindowsProjection>> <>h__TransparentIdentifier0)
0xca51  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>, valuetype [mscorlib]System.Nullable`1<valuetype TimeZoneSyncTask.Data.WindowsProjection>>, bool>::.ctor(object, native int)
0xca56  dup
0xca57  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>, valuetype [mscorlib]System.Nullable`1<valuetype TimeZoneSyncTask.Data.WindowsProjection>>, bool> <>c::<>9__9_6
0xca5c  call     T0x2B000008
0xca61  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>, valuetype [mscorlib]System.Nullable`1<valuetype TimeZoneSyncTask.Data.WindowsProjection>>, class <>f__AnonymousType1`2<int32, valuetype TimeZoneSyncTask.Data.WindowsProjection>> <>c::<>9__9_7
0xca66  dup
0xca67  brtrue.s loc_CA80
0xca69  pop
0xca6a  ldsfld   class <>c <>c::<>9
0xca6f  ldftn    instance class <>f__AnonymousType1`2<int32, valuetype TimeZoneSyncTask.Data.WindowsProjection> <>c::<Sync>b__9_7(class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>, valuetype [mscorlib]System.Nullable`1<valuetype TimeZoneSyncTask.Data.WindowsProjection>> <>h__TransparentIdentifier0)
0xca75  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>, valuetype [mscorlib]System.Nullable`1<valuetype TimeZoneSyncTask.Data.WindowsProjection>>, class <>f__AnonymousType1`2<int32, valuetype TimeZoneSyncTask.Data.WindowsProjection>>::.ctor(object, native int)
0xca7a  dup
0xca7b  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<int32, class TimeZoneSyncTask.Data.WindowsProjectionSet>, valuetype [mscorlib]System.Nullable`1<valuetype TimeZoneSyncTask.Data.WindowsProjection>>, class <>f__AnonymousType1`2<int32, valuetype TimeZoneSyncTask.Data.WindowsProjection>> <>c::<>9__9_7
0xca80  call     T0x2B000009
0xca85  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType1`2<int32, valuetype TimeZoneSyncTask.Data.WindowsProjection>, int32> <>c::<>9__9_8
0xca8a  dup
0xca8b  brtrue.s loc_CAA4
0xca8d  pop
0xca8e  ldsfld   class <>c <>c::<>9
0xca93  ldftn    instance int32 <>c::<Sync>b__9_8(class <>f__AnonymousType1`2<int32, valuetype TimeZoneSyncTask.Data.WindowsProjection> a)
0xca99  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType1`2<int32, valuetype TimeZoneSyncTask.Data.WindowsProjection>, int32>::.ctor(object, native int)
0xca9e  dup
0xca9f  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType1`2<int32, valuetype TimeZoneSyncTask.Data.WindowsProjection>, int32> <>c::<>9__9_8
0xcaa4  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType1`2<int32, valuetype TimeZoneSyncTask.Data.WindowsProjection>, valuetype TimeZoneSyncTask.Data.WindowsProjection> <>c::<>9__9_9
0xcaa9  dup
0xcaaa  brtrue.s loc_CAC3
0xcaac  pop
0xcaad  ldsfld   class <>c <>c::<>9
0xcab2  ldftn    instance valuetype TimeZoneSyncTask.Data.WindowsProjection <>c::<Sync>b__9_9(class <>f__AnonymousType1`2<int32, valuetype TimeZoneSyncTask.Data.WindowsProjection> a)
0xcab8  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType1`2<int32, valuetype TimeZoneSyncTask.Data.WindowsProjection>, valuetype TimeZoneSyncTask.Data.WindowsProjection>::.ctor(object, native int)
0xcabd  dup
0xcabe  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType1`2<int32, valuetype TimeZoneSyncTask.Data.WindowsProjection>, valuetype TimeZoneSyncTask.Data.WindowsProjection> <>c::<>9__9_9
0xcac3  call     T0x2B00000A
0xcac8  stloc.s  0xF
0xcaca  ldloc.s  0xF
  ... truncated ...
```
