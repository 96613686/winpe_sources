# TimeZoneSyncTask.Core.XmlDataTransform::ParseTZI

- ea: `0x123f0`
- end: `0x12530`
- name: `TimeZoneSyncTask.Core.XmlDataTransform::ParseTZI`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x121c0`

## callees

- `0xce30`
- `0xeb30`
- `0xec70`
- `0xec90`
- `0xed40`
- `0xf2f0`
- `0xf310`
- `0xf330`
- `0xf350`
- `0xf4f0`
- `0xf510`
- `0x123f0`
- `0x126b0`

## pseudocode

```c

```

## disassembly

```asm
0x123f0  ldarg.0
0x123f1  ldc.i4.5
0x123f2  newarr   [mscorlib]System.String
0x123f7  dup
0x123f8  ldc.i4.0
0x123f9  ldstr    aUtcoff// "UtcOff"
0x123fe  stelem.ref
0x123ff  dup
0x12400  ldc.i4.1
0x12401  ldstr    aFormat// "Format"
0x12406  stelem.ref
0x12407  dup
0x12408  ldc.i4.2
0x12409  ldstr    aRules// "Rules"
0x1240e  stelem.ref
0x1240f  dup
0x12410  ldc.i4.3
0x12411  ldstr    aLstoff// "LstOff"
0x12416  stelem.ref
0x12417  dup
0x12418  ldc.i4.4
0x12419  ldstr    aUntil// "Until"
0x1241e  stelem.ref
0x1241f  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> TimeZoneSyncTask.Core.XmlDataTransform::ReadXmlAttributes(class [System.Xml]System.Xml.XmlReader reader, string[] rgAttributeNames)
0x12424  stloc.0
0x12425  ldsfld   string[] TimeZoneSyncTask.Core.XmlDataTransform::RgRequiredTziFields
0x1242a  stloc.1
0x1242b  ldc.i4.0
0x1242c  stloc.2
0x1242d  br.s     loc_12454
0x1242f  ldloc.1
0x12430  ldloc.2
0x12431  ldelem.ref
0x12432  stloc.3
0x12433  ldloc.0
0x12434  ldloc.3
0x12435  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x1243a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1243f  ldstr    aUnableToFindRe_0// "unable to find required field {0} in TZ"...
0x12444  ldloc.3
0x12445  ldarg.1
0x12446  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x1244b  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0x12450  ldloc.2
0x12451  ldc.i4.1
0x12452  add
0x12453  stloc.2
0x12454  ldloc.2
0x12455  ldloc.1
0x12456  ldlen
0x12457  conv.i4
0x12458  blt.s    loc_1242F
0x1245a  ldloca.s 4
0x1245c  initobj  TimeZoneSyncTask.Data.TimeZoneRule
0x12462  ldloca.s 4
0x12464  ldloc.0
0x12465  ldstr    aUtcoff// "UtcOff"
0x1246a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x1246f  call     valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Utils.Helper::ParseTimeSpan(string ts)
0x12474  call     instance void TimeZoneSyncTask.Data.TimeZoneRule::set_UtcOffset(valuetype [mscorlib]System.TimeSpan value)
0x12479  ldloca.s 4
0x1247b  ldloc.0
0x1247c  ldstr    aFormat// "Format"
0x12481  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12486  call     instance void TimeZoneSyncTask.Data.TimeZoneRule::set_Format(string value)
0x1248b  ldloca.s 4
0x1248d  ldloca.s 5
0x1248f  initobj  TimeZoneSyncTask.Data.Rule
0x12495  ldloca.s 5
0x12497  ldloc.0
0x12498  ldstr    aRules// "Rules"
0x1249d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x124a2  brtrue.s loc_124A7
0x124a4  ldnull
0x124a5  br.s     loc_124B2
0x124a7  ldloc.0
0x124a8  ldstr    aRules// "Rules"
0x124ad  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x124b2  call     instance void TimeZoneSyncTask.Data.Rule::set_Collection(string value)
0x124b7  ldloca.s 5
0x124b9  ldloc.0
0x124ba  ldstr    aLstoff// "LstOff"
0x124bf  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x124c4  brtrue.s loc_124CD
0x124c6  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0x124cb  br.s     loc_124DD
0x124cd  ldloc.0
0x124ce  ldstr    aLstoff// "LstOff"
0x124d3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x124d8  call     valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Utils.Helper::ParseTimeSpan(string ts)
0x124dd  call     instance void TimeZoneSyncTask.Data.Rule::set_LocalStandardOffset(valuetype [mscorlib]System.TimeSpan value)
0x124e2  ldloc.s  5
0x124e4  call     instance void TimeZoneSyncTask.Data.TimeZoneRule::set_Rules(valuetype TimeZoneSyncTask.Data.Rule value)
0x124e9  ldloca.s 4
0x124eb  ldloc.0
0x124ec  ldstr    aUntil// "Until"
0x124f1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x124f6  brtrue.s loc_12518
0x124f8  ldloca.s 6
0x124fa  initobj  TimeZoneSyncTask.Data.DateTimeEx
0x12500  ldloca.s 6
0x12502  ldsfld   valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Utils.Helper::MaxValue
0x12507  call     instance void TimeZoneSyncTask.Data.DateTimeEx::set_Time(valuetype [mscorlib]System.DateTime value)
0x1250c  ldloca.s 6
0x1250e  ldc.i4.2
0x1250f  call     instance void TimeZoneSyncTask.Data.DateTimeEx::set_Base(valuetype TimeZoneSyncTask.Data.TimeBase value)
0x12514  ldloc.s  6
0x12516  br.s     loc_12528
0x12518  ldloc.0
0x12519  ldstr    aUntil// "Until"
0x1251e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12523  call     valuetype TimeZoneSyncTask.Data.DateTimeEx TimeZoneSyncTask.Data.DateTimeEx::FromString(string s)
0x12528  call     instance void TimeZoneSyncTask.Data.TimeZoneRule::set_Until(valuetype TimeZoneSyncTask.Data.DateTimeEx value)
0x1252d  ldloc.s  4
0x1252f  ret
```
