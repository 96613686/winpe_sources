# TimeZoneSyncTask.Core.XmlDataTransform::ParseTimeZoneMapping

- ea: `0x120f0`
- end: `0x121bb`
- name: `TimeZoneSyncTask.Core.XmlDataTransform::ParseTimeZoneMapping`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0xc6e0`

## callees

- `0xce30`
- `0x120f0`
- `0x126b0`

## pseudocode

```c

```

## disassembly

```asm
0x120f0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x120f5  stloc.0
0x120f6  ldarg.0
0x120f7  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.Stream)
0x120fc  stloc.1
0x120fd  ldloc.1
0x120fe  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x12103  pop
0x12104  br       loc_1219D
0x12109  ldloc.1
0x1210a  ldc.i4.3
0x1210b  newarr   [mscorlib]System.String
0x12110  dup
0x12111  ldc.i4.0
0x12112  ldstr    aTzid// "TZID"
0x12117  stelem.ref
0x12118  dup
0x12119  ldc.i4.1
0x1211a  ldstr    aWinid// "WinID"
0x1211f  stelem.ref
0x12120  dup
0x12121  ldc.i4.2
0x12122  ldstr    aRegion// "Region"
0x12127  stelem.ref
0x12128  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> TimeZoneSyncTask.Core.XmlDataTransform::ReadXmlAttributes(class [System.Xml]System.Xml.XmlReader reader, string[] rgAttributeNames)
0x1212d  stloc.2
0x1212e  ldsfld   string[] TimeZoneSyncTask.Core.XmlDataTransform::RgRequiredMappingFields
0x12133  stloc.3
0x12134  ldc.i4.0
0x12135  stloc.s  4
0x12137  br.s     loc_12163
0x12139  ldloc.3
0x1213a  ldloc.s  4
0x1213c  ldelem.ref
0x1213d  stloc.s  5
0x1213f  ldloc.2
0x12140  ldloc.s  5
0x12142  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x12147  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1214c  ldstr    aUnableToFindRe// "unable to find required field in {0} in"...
0x12151  ldloc.s  5
0x12153  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x12158  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0x1215d  ldloc.s  4
0x1215f  ldc.i4.1
0x12160  add
0x12161  stloc.s  4
0x12163  ldloc.s  4
0x12165  ldloc.3
0x12166  ldlen
0x12167  conv.i4
0x12168  blt.s    loc_12139
0x1216a  ldloc.2
0x1216b  ldstr    aRegion// "Region"
0x12170  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12175  ldstr    a001// "001"
0x1217a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1217f  brfalse.s loc_1219D
0x12181  ldloc.0
0x12182  ldloc.2
0x12183  ldstr    aWinid// "WinID"
0x12188  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x1218d  ldloc.2
0x1218e  ldstr    aTzid// "TZID"
0x12193  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12198  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1219d  ldloc.1
0x1219e  ldstr    aMaptz// "MapTZ"
0x121a3  callvirt instance bool [System.Xml]System.Xml.XmlReader::ReadToFollowing(string)
0x121a8  brtrue   loc_12109
0x121ad  leave.s  loc_121B9
0x121af  ldloc.1
0x121b0  brfalse.s loc_121B8
0x121b2  ldloc.1
0x121b3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x121b8  endfinally
0x121b9  ldloc.0
0x121ba  ret
```
