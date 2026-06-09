# TimeZoneSyncTask.Core.XmlDataTransform::ParseTimeZoneData

- ea: `0x121c0`
- end: `0x123e4`
- name: `TimeZoneSyncTask.Core.XmlDataTransform::ParseTimeZoneData`
- size: `548`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task`

## callers

- `0xc6e0`

## callees

- `0x1050`
- `0xce30`
- `0xcfd0`
- `0x121c0`
- `0x123f0`
- `0x12530`
- `0x126b0`
- `0x127c0`
- `0x127e0`
- `0x127f0`

## pseudocode

```c

```

## disassembly

```asm
0x121c0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>>::.ctor()
0x121c5  stloc.0
0x121c6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>>::.ctor()
0x121cb  stloc.1
0x121cc  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x121d1  stloc.2
0x121d2  ldarg.0
0x121d3  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.Stream)
0x121d8  stloc.3
0x121d9  ldloc.3
0x121da  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x121df  pop
0x121e0  br       loc_123B9
0x121e5  ldloc.3
0x121e6  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x121eb  ldc.i4.1
0x121ec  bne.un   loc_123B9
0x121f1  ldloc.3
0x121f2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x121f7  ldstr    aZone// "Zone"
0x121fc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12201  brfalse  loc_122EB
0x12206  ldloc.3
0x12207  ldc.i4.1
0x12208  newarr   [mscorlib]System.String
0x1220d  dup
0x1220e  ldc.i4.0
0x1220f  ldstr    aId// "ID"
0x12214  stelem.ref
0x12215  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> TimeZoneSyncTask.Core.XmlDataTransform::ReadXmlAttributes(class [System.Xml]System.Xml.XmlReader reader, string[] rgAttributeNames)
0x1221a  dup
0x1221b  ldstr    aId// "ID"
0x12220  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x12225  ldstr    aExpectingZoneI// "expecting zone ID"
0x1222a  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0x1222f  ldstr    aId// "ID"
0x12234  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12239  stloc.s  4
0x1223b  ldarg.1
0x1223c  ldloc.s  4
0x1223e  call     T0x2B00003D
0x12243  brfalse  loc_1238D
0x12248  ldloc.3
0x12249  ldstr    aTzi// "TZI"
0x1224e  callvirt instance bool [System.Xml]System.Xml.XmlReader::ReadToFollowing(string)
0x12253  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12258  ldstr    aExpectingToFin_1// "expecting to find at least one TZI entr"...
0x1225d  ldloc.s  4
0x1225f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x12264  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0x12269  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>::.ctor()
0x1226e  stloc.s  5
0x12270  ldloc.s  5
0x12272  ldloc.3
0x12273  ldloc.s  4
0x12275  call     valuetype TimeZoneSyncTask.Data.TimeZoneRule TimeZoneSyncTask.Core.XmlDataTransform::ParseTZI(class [System.Xml]System.Xml.XmlReader reader, string tzid)
0x1227a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>::Add(var<u1>)
0x1227f  ldloc.3
0x12280  ldstr    aTzi// "TZI"
0x12285  callvirt instance bool [System.Xml]System.Xml.XmlReader::ReadToNextSibling(string)
0x1228a  brtrue.s loc_12270
0x1228c  ldloc.0
0x1228d  ldloc.s  4
0x1228f  ldloc.s  5
0x12291  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>>::set_Item(var<u1>, !!T0)
0x12296  ldloc.2
0x12297  ldloc.s  5
0x12299  ldsfld   class [mscorlib]System.Func`2<valuetype TimeZoneSyncTask.Data.TimeZoneRule, string> <>c::<>9__2_0
0x1229e  dup
0x1229f  brtrue.s loc_122B8
0x122a1  pop
0x122a2  ldsfld   class <>c <>c::<>9
0x122a7  ldftn    instance string <>c::<ParseTimeZoneData>b__2_0(valuetype TimeZoneSyncTask.Data.TimeZoneRule tzr)
0x122ad  newobj   instance void class [mscorlib]System.Func`2<valuetype TimeZoneSyncTask.Data.TimeZoneRule, string>::.ctor(object, native int)
0x122b2  dup
0x122b3  stsfld   class [mscorlib]System.Func`2<valuetype TimeZoneSyncTask.Data.TimeZoneRule, string> <>c::<>9__2_0
0x122b8  call     T0x2B00003E
0x122bd  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__2_1
0x122c2  dup
0x122c3  brtrue.s loc_122DC
0x122c5  pop
0x122c6  ldsfld   class <>c <>c::<>9
0x122cb  ldftn    instance bool <>c::<ParseTimeZoneData>b__2_1(string s)
0x122d1  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x122d6  dup
0x122d7  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__2_1
0x122dc  call     T0x2B00003F
0x122e1  callvirt instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::UnionWith(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x122e6  br       loc_1238D
0x122eb  ldloc.3
0x122ec  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x122f1  ldstr    aRule// "Rule"
0x122f6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x122fb  brfalse  loc_1238D
0x12300  ldloc.3
0x12301  ldc.i4.1
0x12302  newarr   [mscorlib]System.String
0x12307  dup
0x12308  ldc.i4.0
0x12309  ldstr    aName// "Name"
0x1230e  stelem.ref
0x1230f  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> TimeZoneSyncTask.Core.XmlDataTransform::ReadXmlAttributes(class [System.Xml]System.Xml.XmlReader reader, string[] rgAttributeNames)
0x12314  dup
0x12315  ldstr    aName// "Name"
0x1231a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x1231f  ldstr    aExpectingRuleN// "expecting rule name"
0x12324  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0x12329  ldstr    aName// "Name"
0x1232e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12333  stloc.s  6
0x12335  ldloc.2
0x12336  ldloc.s  6
0x12338  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x1233d  brfalse.s loc_1238D
0x1233f  ldloc.3
0x12340  ldstr    aDst// "DST"
0x12345  callvirt instance bool [System.Xml]System.Xml.XmlReader::ReadToFollowing(string)
0x1234a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1234f  ldstr    aExpectingToFin_2// "expecting to find at least one DST entr"...
0x12354  ldloc.s  6
0x12356  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x1235b  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0x12360  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>::.ctor()
0x12365  stloc.s  7
0x12367  ldloc.s  7
0x12369  ldloc.3
0x1236a  ldloc.s  6
0x1236c  call     valuetype TimeZoneSyncTask.Data.DstTransitionRule TimeZoneSyncTask.Core.XmlDataTransform::ParseDST(class [System.Xml]System.Xml.XmlReader reader, string name)
0x12371  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>::Add(var<u1>)
0x12376  ldloc.3
0x12377  ldstr    aDst// "DST"
0x1237c  callvirt instance bool [System.Xml]System.Xml.XmlReader::ReadToNextSibling(string)
0x12381  brtrue.s loc_12367
0x12383  ldloc.1
0x12384  ldloc.s  6
0x12386  ldloc.s  7
0x12388  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>>::set_Item(var<u1>, !!T0)
0x1238d  leave.s  loc_123B9
0x1238f  stloc.s  8
0x12391  call     bool Microsoft.Windows.Staging.Features.Feature_FixBug2886555_TryTraceCatch::get_IsEnabled()
0x12396  brfalse.s loc_123AB
0x12398  ldloc.s  8
0x1239a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1239f  call     T0x2B00000F
0x123a4  call     void TimeZoneSyncTask.TimeZoneSyncTelemetryLogs::TraceError(string format, object[] args)
0x123a9  br.s     loc_123B7
0x123ab  ldloc.s  8
0x123ad  callvirt instance string [mscorlib]System.Exception::get_Message()
0x123b2  call     void [System]System.Diagnostics.Trace::TraceError(string)
0x123b7  leave.s  loc_123B9
0x123b9  ldloc.3
0x123ba  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x123bf  brtrue   loc_121E5
0x123c4  leave.s  loc_123D0
0x123c6  ldloc.3
0x123c7  brfalse.s loc_123CF
0x123c9  ldloc.3
0x123ca  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x123cf  endfinally
0x123d0  newobj   instance void TimeZoneSyncTask.Core.TimeZoneData::.ctor()
0x123d5  dup
0x123d6  ldloc.0
0x123d7  callvirt instance void TimeZoneSyncTask.Core.TimeZoneData::set_MapZoneToRules(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.TimeZoneRule>> value)
0x123dc  dup
0x123dd  ldloc.1
0x123de  callvirt instance void TimeZoneSyncTask.Core.TimeZoneData::set_MapDstToRules(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<valuetype TimeZoneSyncTask.Data.DstTransitionRule>> value)
0x123e3  ret
```
