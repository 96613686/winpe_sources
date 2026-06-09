# TimeZoneSyncTask.Core.IanaRuleTransform::ComputeTransitions

- ea: `0x10970`
- end: `0x10b72`
- name: `TimeZoneSyncTask.Core.IanaRuleTransform::ComputeTransitions`
- size: `514`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0xc6e0`

## callees

- `0xce30`
- `0xea40`
- `0xec70`
- `0xec90`
- `0xf2e0`
- `0xf300`
- `0xf340`
- `0xf4e0`
- `0xf500`
- `0xf730`
- `0xf750`
- `0xf760`
- `0xf770`
- `0xf8e0`
- `0x10970`
- `0x10b80`
- `0x10e00`
- `0x127b0`
- `0x127d0`

## pseudocode

```c

```

## disassembly

```asm
0x10970  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0x10975  stloc.0
0x10976  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0x1097b  stloc.1
0x1097c  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x10981  stloc.2
0x10982  ldloca.s 6
0x10984  initobj  TimeZoneSyncTask.Data.DateTimeEx
0x1098a  ldloca.s 6
0x1098c  ldsfld   valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Utils.Helper::MaxValue
0x10991  call     instance void TimeZoneSyncTask.Data.DateTimeEx::set_Time(valuetype [mscorlib]System.DateTime value)
0x10996  ldloca.s 6
0x10998  ldc.i4.2
0x10999  call     instance void TimeZoneSyncTask.Data.DateTimeEx::set_Base(valuetype TimeZoneSyncTask.Data.TimeBase value)
0x1099e  ldloc.s  6
0x109a0  stloc.3
0x109a1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition>::.ctor()
0x109a6  stloc.s  4
0x109a8  ldnull
0x109a9  stloc.s  5
0x109ab  ldarg.0
0x109ac  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>> TimeZoneSyncTask.Core.TimeZoneData::get_MapZoneToRules()
0x109b1  ldarg.1
0x109b2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>>::ContainsKey(var<u1>)
0x109b7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x109bc  ldstr    aExpectingToFin// "expecting to find rules for tzid {0}"
0x109c1  ldarg.1
0x109c2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x109c7  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0x109cc  ldarg.0
0x109cd  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>> TimeZoneSyncTask.Core.TimeZoneData::get_MapZoneToRules()
0x109d2  ldarg.1
0x109d3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>>::get_Item(void)
0x109d8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>::GetEnumerator()
0x109dd  stloc.s  7
0x109df  br       loc_10B53
0x109e4  ldloca.s 7
0x109e6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype TimeZoneSyncTask.Data.TimeZoneRule>::get_Current()
0x109eb  stloc.s  8
0x109ed  ldloca.s 8
0x109ef  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.TimeZoneRule::get_UtcOffset()
0x109f4  stloc.0
0x109f5  ldloca.s 8
0x109f7  call     instance valuetype TimeZoneSyncTask.Data.DateTimeEx TimeZoneSyncTask.Data.TimeZoneRule::get_Until()
0x109fc  stloc.3
0x109fd  ldloca.s 8
0x109ff  call     instance valuetype TimeZoneSyncTask.Data.Rule TimeZoneSyncTask.Data.TimeZoneRule::get_Rules()
0x10a04  stloc.s  9
0x10a06  ldloca.s 9
0x10a08  call     instance string TimeZoneSyncTask.Data.Rule::get_Collection()
0x10a0d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10a12  brfalse.s loc_10A62
0x10a14  ldloca.s 8
0x10a16  call     instance valuetype TimeZoneSyncTask.Data.Rule TimeZoneSyncTask.Data.TimeZoneRule::get_Rules()
0x10a1b  stloc.s  9
0x10a1d  ldloca.s 9
0x10a1f  call     instance valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Data.Rule::get_LocalStandardOffset()
0x10a24  stloc.1
0x10a25  newobj   instance void TimeZoneSyncTask.Data.Transition::.ctor()
0x10a2a  dup
0x10a2b  ldloc.0
0x10a2c  callvirt instance void TimeZoneSyncTask.Data.Transition::set_UtcOffset(valuetype [mscorlib]System.TimeSpan value)
0x10a31  dup
0x10a32  ldloc.1
0x10a33  callvirt instance void TimeZoneSyncTask.Data.Transition::set_LocalStandardOffset(valuetype [mscorlib]System.TimeSpan value)
0x10a38  dup
0x10a39  ldloc.3
0x10a3a  ldloc.0
0x10a3b  ldloc.1
0x10a3c  call     valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Utils.Helper::ConvertToUtc(valuetype TimeZoneSyncTask.Data.DateTimeEx dtx, valuetype [mscorlib]System.TimeSpan tsUtcOffset, valuetype [mscorlib]System.TimeSpan tsLocalStandardOffset)
0x10a41  callvirt instance void TimeZoneSyncTask.Data.Transition::set_TransitionTime(valuetype [mscorlib]System.DateTime value)
0x10a46  stloc.s  0xA
0x10a48  ldloc.s  5
0x10a4a  brfalse.s loc_10A59
0x10a4c  ldloc.s  5
0x10a4e  ldloc.s  0xA
0x10a50  ldarg.2
0x10a51  ldarg.3
0x10a52  ldloc.s  4
0x10a54  call     void TimeZoneSyncTask.Core.IanaRuleTransform::UpdateCollection(class TimeZoneSyncTask.Data.Transition lastTransition, class TimeZoneSyncTask.Data.Transition transition, int32 minYear, int32 maxYear, class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition> ret)
0x10a59  ldloc.s  0xA
0x10a5b  stloc.s  5
0x10a5d  br       loc_10B33
0x10a62  ldarg.0
0x10a63  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>> TimeZoneSyncTask.Core.TimeZoneData::get_MapDstToRules()
0x10a68  ldloca.s 8
0x10a6a  call     instance valuetype TimeZoneSyncTask.Data.Rule TimeZoneSyncTask.Data.TimeZoneRule::get_Rules()
0x10a6f  stloc.s  9
0x10a71  ldloca.s 9
0x10a73  call     instance string TimeZoneSyncTask.Data.Rule::get_Collection()
0x10a78  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>>::ContainsKey(var<u1>)
0x10a7d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10a82  ldstr    aExpectingToFin_0// "expecting to find rules for DST {0}"
0x10a87  ldloca.s 8
0x10a89  call     instance valuetype TimeZoneSyncTask.Data.Rule TimeZoneSyncTask.Data.TimeZoneRule::get_Rules()
0x10a8e  stloc.s  9
0x10a90  ldloca.s 9
0x10a92  call     instance string TimeZoneSyncTask.Data.Rule::get_Collection()
0x10a97  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x10a9c  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0x10aa1  ldarg.0
0x10aa2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>> TimeZoneSyncTask.Core.TimeZoneData::get_MapDstToRules()
0x10aa7  ldloca.s 8
0x10aa9  call     instance valuetype TimeZoneSyncTask.Data.Rule TimeZoneSyncTask.Data.TimeZoneRule::get_Rules()
0x10aae  stloc.s  9
0x10ab0  ldloca.s 9
0x10ab2  call     instance string TimeZoneSyncTask.Data.Rule::get_Collection()
0x10ab7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>>::get_Item(void)
0x10abc  ldloc.2
0x10abd  ldloc.3
0x10abe  ldloc.0
0x10abf  ldloca.s 1
0x10ac1  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class TimeZoneSyncTask.Data.Transition> TimeZoneSyncTask.Core.IanaRuleTransform::EnumerateDstTransitions(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule> rgDstRules, valuetype [mscorlib]System.DateTime start, valuetype TimeZoneSyncTask.Data.DateTimeEx end, valuetype [mscorlib]System.TimeSpan tsUtcOffset, valuetype [mscorlib]System.TimeSpan& tsLocalStandardOffset)
0x10ac6  ldc.i4.1
0x10ac7  newarr   TimeZoneSyncTask.Data.Transition
0x10acc  dup
0x10acd  ldc.i4.0
0x10ace  newobj   instance void TimeZoneSyncTask.Data.Transition::.ctor()
0x10ad3  dup
0x10ad4  ldloc.0
0x10ad5  callvirt instance void TimeZoneSyncTask.Data.Transition::set_UtcOffset(valuetype [mscorlib]System.TimeSpan value)
0x10ada  dup
0x10adb  ldloc.1
0x10adc  callvirt instance void TimeZoneSyncTask.Data.Transition::set_LocalStandardOffset(valuetype [mscorlib]System.TimeSpan value)
0x10ae1  dup
0x10ae2  ldloc.3
0x10ae3  ldloc.0
0x10ae4  ldloc.1
0x10ae5  call     valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Utils.Helper::ConvertToUtc(valuetype TimeZoneSyncTask.Data.DateTimeEx dtx, valuetype [mscorlib]System.TimeSpan tsUtcOffset, valuetype [mscorlib]System.TimeSpan tsLocalStandardOffset)
0x10aea  callvirt instance void TimeZoneSyncTask.Data.Transition::set_TransitionTime(valuetype [mscorlib]System.DateTime value)
0x10aef  stelem.ref
0x10af0  call     T0x2B00002A
0x10af5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class TimeZoneSyncTask.Data.Transition>::GetEnumerator()
0x10afa  stloc.s  0xB
0x10afc  br.s     loc_10B1C
0x10afe  ldloc.s  0xB
0x10b00  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class TimeZoneSyncTask.Data.Transition>::get_Current()
0x10b05  stloc.s  0xC
0x10b07  ldloc.s  5
0x10b09  brfalse.s loc_10B18
0x10b0b  ldloc.s  5
0x10b0d  ldloc.s  0xC
0x10b0f  ldarg.2
0x10b10  ldarg.3
0x10b11  ldloc.s  4
0x10b13  call     void TimeZoneSyncTask.Core.IanaRuleTransform::UpdateCollection(class TimeZoneSyncTask.Data.Transition lastTransition, class TimeZoneSyncTask.Data.Transition transition, int32 minYear, int32 maxYear, class [mscorlib]System.Collections.Generic.List`1<class TimeZoneSyncTask.Data.Transition> ret)
0x10b18  ldloc.s  0xC
0x10b1a  stloc.s  5
0x10b1c  ldloc.s  0xB
0x10b1e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10b23  brtrue.s loc_10AFE
0x10b25  leave.s  loc_10B33
0x10b27  ldloc.s  0xB
0x10b29  brfalse.s loc_10B32
0x10b2b  ldloc.s  0xB
0x10b2d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10b32  endfinally
0x10b33  ldloc.3
0x10b34  ldloc.0
0x10b35  ldloc.1
0x10b36  call     valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Utils.Helper::ConvertToUtc(valuetype TimeZoneSyncTask.Data.DateTimeEx dtx, valuetype [mscorlib]System.TimeSpan tsUtcOffset, valuetype [mscorlib]System.TimeSpan tsLocalStandardOffset)
0x10b3b  stloc.2
0x10b3c  ldloc.s  5
0x10b3e  callvirt instance valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Data.Transition::get_TransitionTime()
0x10b43  stloc.s  0xD
0x10b45  ldloca.s 0xD
0x10b47  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x10b4c  ldarg.3
0x10b4d  ldc.i4.1
0x10b4e  add
0x10b4f  ble.s    loc_10B53
0x10b51  leave.s  loc_10B6F
0x10b53  ldloca.s 7
0x10b55  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype TimeZoneSyncTask.Data.TimeZoneRule>::MoveNext()
0x10b5a  brtrue   loc_109E4
0x10b5f  leave.s  loc_10B6F
0x10b61  ldloca.s 7
0x10b63  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype TimeZoneSyncTask.Data.TimeZoneRule>
0x10b69  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10b6e  endfinally
0x10b6f  ldloc.s  4
0x10b71  ret
```
