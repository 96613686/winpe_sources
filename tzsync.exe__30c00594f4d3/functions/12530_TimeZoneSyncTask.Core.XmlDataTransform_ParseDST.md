# TimeZoneSyncTask.Core.XmlDataTransform::ParseDST

- ea: `0x12530`
- end: `0x126a5`
- name: `TimeZoneSyncTask.Core.XmlDataTransform::ParseDST`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task`

## callers

- `0x121c0`

## callees

- `0xce30`
- `0xeb30`
- `0xec20`
- `0xef60`
- `0xf040`
- `0xf060`
- `0xf080`
- `0xf0a0`
- `0xf0c0`
- `0xf0e0`
- `0xf100`
- `0xf6c0`
- `0x12530`
- `0x126b0`

## pseudocode

```c

```

## disassembly

```asm
0x12530  ldarg.0
0x12531  ldc.i4.7
0x12532  newarr   [mscorlib]System.String
0x12537  dup
0x12538  ldc.i4.0
0x12539  ldstr    aFrom// "From"
0x1253e  stelem.ref
0x1253f  dup
0x12540  ldc.i4.1
0x12541  ldstr    aTo// "To"
0x12546  stelem.ref
0x12547  dup
0x12548  ldc.i4.2
0x12549  ldstr    aIn// "In"
0x1254e  stelem.ref
0x1254f  dup
0x12550  ldc.i4.3
0x12551  ldstr    aOn// "On"
0x12556  stelem.ref
0x12557  dup
0x12558  ldc.i4.4
0x12559  ldstr    aAt// "At"
0x1255e  stelem.ref
0x1255f  dup
0x12560  ldc.i4.5
0x12561  ldstr    aSave// "Save"
0x12566  stelem.ref
0x12567  dup
0x12568  ldc.i4.6
0x12569  ldstr    aLetter// "Letter"
0x1256e  stelem.ref
0x1256f  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> TimeZoneSyncTask.Core.XmlDataTransform::ReadXmlAttributes(class [System.Xml]System.Xml.XmlReader reader, string[] rgAttributeNames)
0x12574  stloc.0
0x12575  ldsfld   string[] TimeZoneSyncTask.Core.XmlDataTransform::RgRequiredDstFields
0x1257a  stloc.s  4
0x1257c  ldc.i4.0
0x1257d  stloc.s  5
0x1257f  br.s     loc_125AD
0x12581  ldloc.s  4
0x12583  ldloc.s  5
0x12585  ldelem.ref
0x12586  stloc.s  6
0x12588  ldloc.0
0x12589  ldloc.s  6
0x1258b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x12590  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12595  ldstr    aUnableToFindRe_1// "unable to find required field {0} in DS"...
0x1259a  ldloc.s  6
0x1259c  ldarg.1
0x1259d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0x125a2  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0x125a7  ldloc.s  5
0x125a9  ldc.i4.1
0x125aa  add
0x125ab  stloc.s  5
0x125ad  ldloc.s  5
0x125af  ldloc.s  4
0x125b1  ldlen
0x125b2  conv.i4
0x125b3  blt.s    loc_12581
0x125b5  ldloc.0
0x125b6  ldstr    aFrom// "From"
0x125bb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x125c0  call     int32 TimeZoneSyncTask.Utils.Helper::ParseInt32(string s)
0x125c5  stloc.1
0x125c6  ldloc.0
0x125c7  ldstr    aTo// "To"
0x125cc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x125d1  brtrue.s loc_125DF
0x125d3  ldsflda  valuetype [mscorlib]System.DateTime TimeZoneSyncTask.Utils.Helper::MaxValue
0x125d8  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x125dd  br.s     loc_125EF
0x125df  ldloc.0
0x125e0  ldstr    aTo// "To"
0x125e5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x125ea  call     int32 TimeZoneSyncTask.Utils.Helper::ParseInt32(string s)
0x125ef  stloc.2
0x125f0  ldloc.0
0x125f1  ldstr    aIn// "In"
0x125f6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x125fb  call     int32 TimeZoneSyncTask.Utils.Helper::ParseInt32(string s)
0x12600  stloc.3
0x12601  ldloc.1
0x12602  ldloc.2
0x12603  cgt
0x12605  ldc.i4.0
0x12606  ceq
0x12608  ldstr    aExpectingFromT// "expecting From <= To"
0x1260d  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0x12612  ldloc.3
0x12613  ldc.i4.1
0x12614  blt.s    loc_12620
0x12616  ldloc.3
0x12617  ldc.i4.s 0xC
0x12619  cgt
0x1261b  ldc.i4.0
0x1261c  ceq
0x1261e  br.s     loc_12621
0x12620  ldc.i4.0
0x12621  ldstr    aExpectingInInR// "expecting In in range [1, 12]"
0x12626  call     void TimeZoneSyncTask.TimeZoneSync::Require(bool cond, string msg)
0x1262b  ldloca.s 7
0x1262d  initobj  TimeZoneSyncTask.Data.DstTransitionRule
0x12633  ldloca.s 7
0x12635  ldloc.1
0x12636  call     instance void TimeZoneSyncTask.Data.DstTransitionRule::set_From(int32 value)
0x1263b  ldloca.s 7
0x1263d  ldloc.2
0x1263e  call     instance void TimeZoneSyncTask.Data.DstTransitionRule::set_To(int32 value)
0x12643  ldloca.s 7
0x12645  ldloc.3
0x12646  call     instance void TimeZoneSyncTask.Data.DstTransitionRule::set_In(int32 value)
0x1264b  ldloca.s 7
0x1264d  ldloc.0
0x1264e  ldstr    aOn// "On"
0x12653  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12658  call     valuetype TimeZoneSyncTask.Data.DayOfMonth TimeZoneSyncTask.Data.DayOfMonth::FromString(string s)
0x1265d  call     instance void TimeZoneSyncTask.Data.DstTransitionRule::set_On(valuetype TimeZoneSyncTask.Data.DayOfMonth value)
0x12662  ldloca.s 7
0x12664  ldloc.0
0x12665  ldstr    aAt// "At"
0x1266a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x1266f  call     valuetype TimeZoneSyncTask.Data.TimeOfDay TimeZoneSyncTask.Data.TimeOfDay::FromString(string s)
0x12674  call     instance void TimeZoneSyncTask.Data.DstTransitionRule::set_At(valuetype TimeZoneSyncTask.Data.TimeOfDay value)
0x12679  ldloca.s 7
0x1267b  ldloc.0
0x1267c  ldstr    aSave// "Save"
0x12681  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x12686  call     valuetype [mscorlib]System.TimeSpan TimeZoneSyncTask.Utils.Helper::ParseTimeSpan(string ts)
0x1268b  call     instance void TimeZoneSyncTask.Data.DstTransitionRule::set_Save(valuetype [mscorlib]System.TimeSpan value)
0x12690  ldloca.s 7
0x12692  ldloc.0
0x12693  ldstr    aLetter// "Letter"
0x12698  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x1269d  call     instance void TimeZoneSyncTask.Data.DstTransitionRule::set_Letter(string value)
0x126a2  ldloc.s  7
0x126a4  ret
```
